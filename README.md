# Java-
个人java学习笔记
day1:
#1
public class 类名{
public static void main(String args[]){
  执行语句
  }
}

分析：用class定义了一个类，类是Java的基本封装单元，public表示为公共类，只能有一个公共类，该类为主类。
{}main()方法：一个程序中只能有一个main()方法，为该程序的执行入口，且必须由public static void main(String args[])语句来定义。
public表示为公共方法；static表示为静态方法，属于类的方法，可通过类名直接调用；void表示此方法没有返回值;String args[]是main()方法传递的参数。
#2 
编译源程序：cmd进入DOS命令窗口，输入：
d:                          //改变盘符为D盘
cd 目录名                   //当前目录为...
javac 文件名                //编译

#3注释
// 注释单行  /*...*/注释多行 /**...**/注释文档

#4
基本数据输入及输出
输入：read()方法，此时必须使用“异常机制”，在出现异常时，由Java自行解决（即抛出异常），代码如下
public class 类名{
public static void main(String args[])throws IOException{
  char c；
  System.out.print("输入：")；
  c=(char)System.in.read();
  System.out.print("输入为："+c)；
  }  
}  
  Scannar类输入：用到.next方法（有nextInt、nextString、nextDouble等等），代码如下
 import java.util.*
 public class 类名{
 public static void main(String args[]){
    System.out.print("输入：")；
    Scannar a=new Scannar(System.in);
    int b=a.nextInt();
    System.out.print("输入为："+b)；
  }
}
输出：.out（）方法

#5
选择结构                          
if嵌套语句结构：                     switch语句
if(条件1){                          从多个分支中选择一个来执行
  //语句1                           switch(表达式){                                              }
}else if(条件2){                        case1 常量表达式：
  //语句2                               语句1;
} ...                                   break;(可选)
  ...                                   case1 常量表达式：
  ...                                   语句2;
 }else{                                 break;(可选)
  //结束语句                             ...
 }                                      default:
                                        结束语句     //默认处理的语句
 #5
 循环语句
 while与do--while(先执行循环，再判断)  for(int i=1;i<=100;i++){}  嵌套循环 ------------------省略
 
 #6
 中断流程控制
 break(1 用在switch以分割成功匹配的代码段  2 用在循环中以结束循环)
 continue(用在循环体内结束本次循环，跳转到循环的开始位置)
 return(与循环无关，中断函数并返回到一个数据，如果在循环中使用，则直接跳转到循环所在函数的结尾)
 
 #7
 一维数组:int a[]=new int[5]; 或者int a[]={1,2,3,4,5} ;    其中new为关键字，为数组创建空间并初始化
 二维数组:int b[][]=new int[4][5]; 或者int b[][]={{1,2},{3,4,5}};
 数组排序（略） 
 
 #8
 方法:又被称为函数、过程、子程序；封装在类中
 1 定义：[方法修饰符]返回值类型 方法名([形式化参数表])[throws 异常列表]{           
               //方法体
 }
 说明：方法修饰符：指定使用范围，可以是public、private、protected、static、final等
      返回值类型：既可以是基本数据类型，也可以是数组、类等，没有返回值，则用void表示，有则需要写return语句
      方法名：符合驼峰命名法，如setName
      形式化参数表:方法需要输入的参数，任意数量，用","隔开 
 2 调用：实参传递给形参的过程
 3 重载：一个类中可以定义多个同名的方法，但各个方法具有不同的参数类型或者个数，用于解决功能类似但是参数不同的一组方法。
 4 嵌套和递归：在一个方法体中调用了另一种方法---嵌套；在一个方法体中直接或者间接的调用了自身---递归
 
 #9
 类与对象(Object Oriented OO)
 格式：类的修饰符 class 类名 [extends 父类名]{
      成员变量的定义；
      成员方法的定义；
 } 
 补充：成员变量的属性是private时，成员方法用get---set方法
 示例：{
       private double x;
       private double y;
       ...
       }
       pbulic double getX(){    //获取圆心坐标
              return x;
       }
       public void setX(double x1){   //设置圆心的坐标
              x=x1;
       }
 构造方法和对象初始化：在申明一个对象引用后，要用new运算符（如 Circle circle1=new Circle();）为新对象分配空间，其实就是要调用构造方法，在java中，使用构造方法是生成实例对象的唯一方法。
 示意：public class Xyz{
            private int x;
            public Xyz(){    //带一个参数的构造方法
                  x=i;
            }
 }
 构造方法的调用：Xyz xyz1=new Xyz(3);
 构造方法的重载：一个类可以有多个不同参数列表的构造方法，可以用关键词this来指代本类中的其他构造方法。
 示例：public Circle1(int a1,int b1,int c1){
            a=a1;
            ...
 }
 面向对象三大特征：1 封装：类是封装的基本单元
使用private修饰的属性和方法只能在本类中被访问，get()set()方法就是为了封装而设计的。
    2  继承：子类可以继承父类的属性和方法，从而简化程序设计。
结构：   编写父类
        class Pet{
         //属性和方法为public公共
}       
         编写子类
        class Dog extends Pet{
        //子类特有的属性和方法
}
        class Cat extends Pet{
}
说明：//子类继承了父类的非私有的属性和方法
      //在java中父类可以被多个子类继承，而子类只可以继承自一个父类（python中子类可以继承自多个父类）
      //当子类中有方法和主类同名时，子类优先，成为方法重写（或者方法复写）。
//三种情况下没法继承：1 父类属性为private(私有) 2 子类和父类不在同一个包中（可以通过导包来解决） 3 构造方法（父类中的无参构造方法可以被继承）
补充：四种修饰符：public(所有) private(本类) 默认（friendly)(本类和同包) protected(本类 同包 子包)
关键字：super----子类访问父类成员（构造方法，属性，方法等）
调用构造方法时，需要卸载构造方法里面的第一句，如：
          public Dog(Stiring name,String color,int age){
               super(name,color,age);  
}
//也可以把子类自己的属性加进去，如：
 String strain;
 public Dog(Stiring name,String color,int age,String strain){
               super(name,color,age);
               this.strain=strain;
调用方法和属性时。用super.属性和super.方法即可
       final-------可以修饰类、方法、变量（类不能被继承，方法不可以被子类重写，变量值不可以改变）
final写在修饰符前面，如final public class Pet(){};final double pai=3.1415926;
3  多态：同一个引用类型，使用不同的示例而执行不同的操作。
使用多态的条件:编写具有继承关系的父类和子类；子类重写父类方法；父类引用指向子类的对象。
示例：
package com.duotai;
public class Master {
    //pet可以是Pet子类的实例
    public void feed(Pet pet){
        System.out.println("开始喂食");
        pet.eat();
    }
}
//Cat、Dog为子类（其中有eat方法）Pet为主类（其中也有eat方法，但主类为抽象类，eat方法也为抽象方法）
public class Test {
    public static void main(String[] args) {
        Master master=new Master();
        Cat cat=new Cat();
        Dog dog=new Dog();//向上转型（自动的）

        master.feed(dog);

    }
}


#10 
类的扩展
Object类（所有类的最终父类） public class Pet extends Object{};
其中的.equals()方法与==意义相同
抽象类：java中使用abstract抽象类，来限制实例化（如限制父类实例化）
示例： public abstract class Pet{};
//抽象类中有普通方法也有抽象方法，抽象方法一般不用在构造方法中，抽象类中的抽象方法，子类必须实现（即重写，除非子类也是抽象类）
//为继承而生
接口类：解决无法多继承的问题（interface 只能修饰类）
结构： public interface MyInterFace{
       public viod foo();   //所有方法都是 public abstract
}；
//接口不可以被实例化
//接口类必须实现接口类的所有方法，即所有方法都是 public abstract
//一个类可以实现多个接口
//接口类的变量都是静态变量
//没有构造方法
结构：首先编写一个Interface类，如
package com.jiekou;
public interface Mp3 {
    String discrib="这是一个Mp3接口";
    public abstract void playMusic();
}
再构造一个Cellphone类来实现这个接口类，如
package com.jiekou;
public class CellPhone extends Phone implements Mp3 {
    @Override
    public void playMusic() {
        System.out.println("开始播放音乐");
    }

    @Override
    public void call() {
        System.out.println("开始打电话");
    }
}
再构造一个CellPhone来继承的父类Phone类，如
package com.jiekou;
public  abstract class Phone {
    public abstract void call();
}
最后构造一个测试类，如
package com.jiekou;
public class Test {
    public static void main(String[] args) {
    CellPhone cp=new CellPhone();
    cp.playMusic();
    cp.call();
    }
}
描述：接口表示一种能力，这体现在接口的方法上。面向接口编程时，关心实现类有何能力，而不关心实现细节；面向接口的约定而不关心接口的具体实现。
多接口的实现：在原有类的基础上，构造额外的接口类，在接口类的实现类中添加接口类，如：public class CellPhone extends Phone implements Mp3,Map,Wallet{}；
再添加新的接口类中的方法即可。
#11
异常处理以及程序调试
package com.yichang;

//已知可能出现异常的代码段，即无需抛出异常
public class Test1 {
    public static void main(String[] args) {
        int[] array1={12,31,32,4,4,3434,43,0,32,4,43,5};
        for(int x:array1){
            try{   //不会出现异常的代码
                int y=100/x;
                System.out.println(".......");
            }catch (Exception e){
                System.out.println("出现异常");
                e.printStackTrace();
                System.exit(1);//手动退出
            }finally {//无论是否有异常，都会执行的代码,除非手动退出
                System.out.println("本次循环执行结束");
            }
        }




    }
}
---------------------------------------
package com.yichang;
//未知可能出现异常的代码段，即需要抛出异常
public class Test2 {
    public static void function1(int i) throws Exception{
        //可能出现异常的代码段
        int y=100/i;
        System.out.println("100除以"+i+"结果是"+y);
    }
    public static void main(String[] args) {
        int[] array1={12,31,32,4,4,3434,43,0,32,4,43,5};
        for(int x:array1){
            try {
                function1(x);

            }catch (Exception e){
                e.printStackTrace();
            }

        }
    }
}
-------------------------------
package com.yichang;

import java.util.Scanner;

//自定义异常
public class Test3 {
    public static void main(String[] args)  {
        Scanner s=new Scanner(System.in);
        System.out.println("请输入你的密码（长度必须为6位：）");
        String psw=s.next();

        if(psw.length()==6){
            System.out.println("密码设置成功");
        }else {
            System.out.println("密码设置失败");
            try {
                throw new Exception("密码必须为6位"); //这就是自定义异常，括号中是我们定义的错误提示信息
            } catch (Exception e) {
                e.printStackTrace();
            }


        }
    }
}

