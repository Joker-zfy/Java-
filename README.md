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
{}main()方法：一个程序中只能有一个main()方法，为该程序的执行入口，且必须由public static void main(Sting args[])语句来定义。
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
