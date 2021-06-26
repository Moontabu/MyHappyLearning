本周总结6.21-6.25：  

一：关于Unity实际操作中的问题：
=================================

1、关于NullReferenceException: Object reference not set to an instance of an object
-----------------------------------------------------------------------

这次的代码，在运行的时候一直都出现NullReferenceException: Object reference not set to an instance of an object这个错误，导致我在这个错误上来来回回弄好多个小时，最后终于把这个问题解决了。

那么导致这个错误的原因是我一直没有在unity界面设置Enemy上面的数字，但是我的代码里面却有声明还有调用，这样就导致我的代码在执行的时候没有实例对象，当我添加上了TXEX之后，就好啦！  

2、关于在TXEX改变了文字后，game界面依然显示默认文字问题  
--------------

那是因为我的粗心，把代码写错了    

  ```
  heathText.text = heathText.ToString();
  改成
  heathText.text = heathPoint.ToString();
  ```

3、关于我的cube不与enemy发生碰撞的问题  
-----------------
按照老师给我的网址，重新设置了Project Settings里面的参数，然鹅还是没有得到解决。  
最终原因：  
**物体发生碰撞的必要条件：
两个物体都必须带有碰撞器(Collider)，其中一个物体还必须带有Rigidbody刚体**  
给enemy加上了rigidbody之后完美解决。  
>**拓展：  
发生碰撞的必要条件是什么？   
1：两个物体都必须带有碰撞盒。  
2：至少有一个物体带有Rigidbody组件。  
3：两个物体要发生相对位移。**  

4、Z-Fighting的问题
---------------
从上周开始我的scene面板就一直出现了模糊和花的迹象，之前老师给我说过一次我没记住，这次在老师的帮助和查阅资料的情况下解决了。  
其实根本问题就是“重面”，我们只需要简单的解决重面就可以了，调高或者拉低任意一个重面的对象。  

5、在enemy上的数字显示的时候反复跳动  
-----------------------------
这个我们的重面有些相似，是因为我们的渲染器在渲染的时候反复切换统一深度的对象导致的。所以我们把文字的高度稍微调高就解决了。

二：对于泛型的理解
=========
在 C# 语言中泛型方法是指:通过泛型来约束方法中的**参数类型**，也可以理解为**对数据类型设置了参数**。

如果没有泛型，每次方法中的参数类型都是固定的，不能随意更改。

在使用泛型后，方法中的数据类型则由指定的泛型来约束，即可以根据提供的泛型来传递不同类型的参数。  
【比如我们可以直接把 float 转 int】

需要注意的是：定义泛型方法需要在方法名和参数列表之间加上<>，并在其中使用 T 来代表参数类型。

也可以使用其他的标识符来代替参数类型， 但通常都使用T来表示。

1）List泛型集合
----
简单来说，就是不同类型之间的简化转化  
```
class Person
{
    private string _name; //姓名
    private int _age; //年龄
    
    //创建Person对象
    public Person(string Name, int Age)
    {
        this._name= Name;
        this._age = Age;
    }
    
    //姓名
    public string Name
    {
        get { return _name; }
    }
    
    //年龄
    public int Age
    {
        get { return _age; }
    }
}

//创建Person对象
Person p1 = new Person("王", 22);
Person p2 = new Person("蹇", 24);
Person p3 = new Person("苟", 18);

//创建类型为Person的对象集合
List<Person> persons = new List<Person>();

//将Person对象放入集合
persons.Add(p1);
persons.Add(p2);
persons.Add(p3);


Console.Write(persons[1].Name);
//代码部分copy了网上的~~~~~
```


三：对象池解析
======
**对象池——就是将对象存储在一个池子中，当需要时再次使用，而不是每次都实例化一个新的对象。**  

(这段我抄的）对象池包含了4个类。这4个类的作用分别是：

1).ResPool            

 以一类GameOjbect划分为一类对象池。而每一类对象池又以一个字符串的key作为索引。ResPool 便是对象池个体的包装。

2).ResPoolMgr

 故名思意这是一个管理众多（ResPool）对象池个体的类。ResPool与ResPoolMgr属于聚合关系。ResPoolMgr包含ResPool对象，但ResPool并不是ResPoolMgr的一部分。

3).AssetMgr 

通常AssetMgr这一层打交道的一般是所有资源的加载管理，包括AssetBundle、Resource、AssetDataBase各种同步异步等。

4).PoolKeyDefine

 PoolKeyDefine仅仅作为一个ResPool的key的定义类，抽离出来的目的是由于项目中要做大量的频繁修改。根据对象的开闭包装原则，我们最不希望的是修改编码的时候来轻易侵入触动我们设计的核心类里。  
 
>**使用对象池有几个注意点：**

>1.虽然对象池可以优化对象利用率，但是对象池也不能无限地存储对象，这样对于内存占用也是急剧增加，应该通过限制池子上限，并通过统计获取使用频率较低的对象并剔除，从而动态地收缩对象池；

>2.对于重复使用的对象，在对象池中应该处理好对象重置（reset）的操作；

>3.假如在多个线程中同时访问统一对象池，要处理好线程安全的问题。   

本周期望讲解的知识点
===
1、泛型List的使用（本周作业中如何管理预制体按照我们的要求生成)  
2、泛型的理解  
3、对象池的理解  
4、C#的语法基础知识及运用
