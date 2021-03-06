### 使用继承改进程序

#### 新建一个类`Animal.cs`,这个类是`Cat.cs`和`Dog.cs`的基类,包含了两个类中类似的属性和方法。

```cs
class Animal
{
  public string Name { get; set; }//名字
  public string Color { get; set; }//颜色
  public string Kind { get; set; }//种类
  public string Favorite { get; set; }//喜好

  //自我介绍
  public void Introduce()
  {
    string info = string.Format("我是漂亮的{0}，我的名字叫{1}，身穿{2}的衣服，我爱吃{3}！",
        Kind, Name, Color, Favorite);
    Console.WriteLine(info);
  }
}
```

#### `Cat.cs`

```cs
class Cat : Animal
{
    //跳舞
    public void Dancing()
    {
        Console.WriteLine("下面我给大家表演《小猫迪斯科》，请大家鼓掌啊：>");
    }
}
```

#### `Dog.cs`

```cs
class Dog : Animal
{
    //赛跑
    public void Race()
    {
        Console.WriteLine("下面我给大家表演《狗狗精彩百米跨栏》，请大家鼓掌啊：>");
    }
}
```

#### `Program.cs`

```cs
class Program
{
    static void Main(string[] args)
    {
        //创建一只狗和一只猫
        Cat objCat = new Cat() { Name = "球球儿", Color = "黄色", Kind = "小花猫", Favorite = "小鱼" };
        Dog objDog = new Dog() { Name = "棒棒", Color = "黑色", Kind = "小黑狗", Favorite = "排骨" };
        Console.WriteLine("主人要求她们做自我介绍......");
        Console.WriteLine();
        //调用各自的方法
        objCat.Introduce();
        objDog.Introduce();
        Console.WriteLine();
        Console.WriteLine("主人要求她们表演节目......");
        objCat.Dancing();
        objDog.Race();
        Console.ReadLine();
    }
}
```
