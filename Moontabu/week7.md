2021.7.12-2021.7.17总结：  

本周心得：  
-------
本周我们开始自己做坦克游戏，很明显感觉到这次的练习比之前要有想法很多，在C#语法上面也更加熟练一些了。在制作过程中，我脑子里不断的冒出新想法，然后就赶紧去查实现我思路的方法。  
虽然是只使用了一些我能理解的简单的，复杂的我还没办法做到，但是我认为这是一个好的开始，有了这样的想法，然后去查阅资料，再去实践在项目中，最后成功，这种喜悦是无法用言语来描述的。  
下周我将继续延续我本周的方式去做，感觉坦克游戏做完那天，我回收获很多。  

本周阅读  
---
本周我阅读的专辑是：有趣的心理学，其中有一篇文章我觉得写的挺好的，叫《被打扰真的会干扰你做事情吗？》。  
文章讲的是一个科学家做的实验，实验最终表明的是：专注于做一件事的时候，被打扰反而会加深你对这件事的印象，在面对卡壳的时候，休息一下或者即兴中断一下，反而肯能是取得进展的关键。  






本周新学代码：  
---

**- 每秒相同伤害的代码**
```
public class TankBullet : MonoBehaviour
{
    public int TankDamage = 10;//声明伤害值
    private float tempTime = 0;
    public float cd = 1f;//声明cd时间
    void Start()
    {
        
    }
    
    void Update()
    {
        
    }
    private void OnTriggerEnter(Collider other)
    {
        if (other.gameObject.tag=="Enemy")
        {
            if (Time.time-tempTime>cd)//当游戏运行时间大于我们的CD时间 这段代码就运行一次
            {
                other.gameObject.GetComponent<TankBlood>().TakeDamage(TankDamage);
                //由于我们是无限的在减血 所以要设置一个减血的间隔时间
                tempTime = Time.time;  // tempTime等于当前时间
              
                // tempTime不变，Time.time会一直增长
                // Time.time增长到减去tempTime的值大于cd时间之后，代码就回到最初的判断条件，又会被调用一次
            }
            
        }
    }
}
```


    
**- 角色的转向移动**
```
 void Update()
    {
        //=================角色的前进后退和转向====================
        if(Input.GetKey(KeyCode.W)) 
        {
            this .transform .Translate (Vector3.forward *Time .deltaTime*speed );
        }
        else if(Input.GetKey(KeyCode.S))
        {
            this .transform .Translate (Vector3.forward *Time .deltaTime*-speed );
        }
        if(Input.GetKey(KeyCode.A )) 
        {
            this .transform .Rotate (Vector3.up *Time .deltaTime*-rotatespeed);
        }
        else if(Input.GetKey(KeyCode.D))
        {
            this .transform .Rotate (Vector3.up *Time .deltaTime*rotatespeed);
        }
    }
    //需要注意的是，先声明speed和rotatespeed的值，然后在update里面写方法
    //利用if else判断进行移动
```




**- 为角色添加血条**
```
public class TankBlood : MonoBehaviour
{
    public int Blood = 100;//最大生命值
    public int currentBlood;//获取当前生命值
    void Start()
    {
        currentBlood = Blood;//使当前生命值赋予角色
    }
```  
    
    
    
    
    
    
    
 本周新学会的unity技巧和知识：
 ---
 
 
>**is trigger**

在Collider里面勾选了这个，我们就可以把这个对象当作一个虚拟的“实体”，不会对其他的对象产生碰撞，而只是检测我们设置好的满足条件的碰撞的对象。  

>**unity中实现双人操作游戏** 

（即：WASD与上下左右键单独控制角色）  
在unity界面中，Edit--Input--分别复制一个横向与纵向--设置好分别的名称--代码里面设置调用--完成。  

>**关于状态机**  

状态机的四大概念：  

1 State ，状态。一个状态机至少要包含两个状态。例如上面自动门的例子，有 open 和 closed 两个状态。  

2 Event ，事件。事件就是执行某个操作的触发条件或者口令。对于自动门，“按下开门按钮”就是一个事件。  

3 Action ，动作。事件发生以后要执行动作。例如事件是“按开门按钮”，动作是“开门”。编程的时候，一个 Action 一般就对应一个函数。  

4 Transition ，变换。也就是从一个状态变化为另一个状态。例如“开门过程”就是一个变换。  

>**SendMessage**  
作用：调用一个对象的函数，这个函数可以是公有的也可以是私有的。  
功能：用于向某个特定的Gameobject，让他完成指定的功能。  
本质：调用那个GameObject里面Script里的函数。  


>**延迟销毁游戏对象**  

默认情况下，使用Destory(）方法会立即销毁对象，如果想要延迟一段时间销毁，可在方法中传递一个时间参数，例如：  
```
Dessroy(gameobject,2f)
```  
>**做随机一个值**  
之前了解过Random.xxxx，了解了之后在这次的坦克游戏中我就用到了一个随机的方式，如下：  
```
public void TakeDamage()
    {
        if (blood <= 0)

            return;
        blood -= Random.Range(10, 20);
        if (blood <= 0)
        {
            //坦克血量为0等时候，播放坦克爆炸的声音（播放位置就是当前坦克的位置）
            AudioSource.PlayClipAtPoint(tankExplosionAudio, transform.position);
            //播放爆炸效果
            GameObject.Instantiate(tankExplosion, transform.position + Vector3.up, transform.rotation);
            GameObject.Destroy(this.gameObject);//血量为0时摧毁坦克
        }
    }
    
 ```  
  >**在Inspector中显示私有变量**  
  可以把私有变量标记为SerializeField,就可以在Inspector中显示。例如：  
  ```
  【SerializeField】
  private int unmber=1;
  ```
  
>**在Inspector中隐藏公有变量**  
如果不希望在Inspector中显示共有变量，可以把变量标记为HideinInspector。例如：  
```
[HideinInspector]
public int unmber=2;
```  

