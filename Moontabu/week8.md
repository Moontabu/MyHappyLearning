有限状态机
--
>有限状态机FSM的要点是：

拥有一组状态，并且可以在这组状态之间进行切换。比如我们举个例子：一个游戏主角是个英雄，我们要控制英雄的是站立，跳跃（按↑键），蹲下（按↓键）和跳斩（在跳跃途中按了下方向键）。  

1.状态机同时只能在一个状态。英雄不可能同时处于跳跃和站立。事实上，防止这点是使用FSM的理由之一。  

2.一连串的输入或事件被发送给机器。在我们的例子中，就是按键按下和松开。  

3.每个状态都有一系列的转换，转换与输入和另一状态相关。当输入进来，如果它与当前状态的某个转换匹配，机器转为转换所指的状态。  

举个例子，在站立状态时，按下下键转换为俯卧状态。在跳跃时按下下键转换为跳斩。如果输入在当前状态没有定义转换，输入就被忽视。

目前而言，游戏编程中状态机的实现方式，有两种可以选择：

1- 用枚举配合switch case语句。  

2- 用多态与虚函数（也就是状态模式）。

用状态模式实现状态机
--
状态模式的实现要点，主要有三点：

**1.为状态定义一个接口。**  
首先，我们为状态定义一个接口。每一个与状态相关的行为都定义成虚函数。对于上文的例子而言，就是handleInput和update函数。
```
class HeroineState
{
public:
	virtual ~HeroineState( ) {}
	virtual void handleInput(Heroine& heroine, Input input) {}
	virtual void update(Heroine& heroine) {}
};
```





**2.为每个状态定义一个类.**  

对于每一个状态，我们定义了一个类并继承至此状态接口。它覆盖的方法定义主角对应此状态的行为。换句话说，把之前的switch语句里面的每个case语句中的内容放置到它们对应的状态类里面去。比如：

```
class DuckingState : public HeroineState
{
public:
	DuckingState( )
		:chargeTime_(0)
	{ }
 
	virtual void handleInput(Heroine& heroine, Input input) {
		if (input == RELEASE_DOWN)
		{
			// Change to standing state...
			heroine.setGraphics(IMAGE_STAND);
		}
	}
 
	virtual void update(Heroine& heroine) {
		chargeTime_++;
		if (chargeTime_ > MAX_CHARGE)
		{
			heroine.superBomb( );
		}
	}
 
private:
	int chargeTime_;
}; 
```
在这里我们也将chargeTime_移出了Heroine，放到了DuckingState（下蹲状态）类中。 因为这部分数据只在这个状态有用，这样符合设计的原则。  

**3.恰当地进行状态委托。**  

接下来，我们在主角类Heroine中定义一个指针变量，让它指向当前的状态。放弃之前巨大的switch，然后让它去调用状态接口的虚函数，最终这些虚方法就会动态地调用具体子状态的相应函数了：

 
```
class Heroine
{
public:
	virtual void handleInput(Input input)
	{
		state_->handleInput(*this, input);
	}
 
	virtual void update( )
	{
		state_->update(*this);
	}
 
	// Other methods...
private:
	HeroineState* state_;
};
```

而为了“改变状态”，我们只需要将state_声明指向不同的HeroineState对象。至此，经过为状态定义一个接口，为每个状态定义一个类以及进行状态委托，经历这三步，就是的状态模式的实现思路了。  

为方便之后继续查阅，原文链接：  
https://qianmo.blog.csdn.net/article/details/52824776?utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7Edefault-5.control&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7Edefault-5.control
