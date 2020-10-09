# Java多态

## 概念
- 多态，是面向对象的程序设计语言最核心的特征。多态，意味着一个对象有着多重特征，可以在特定的情况下，表现不同的状态，从而对应着不同的属性和方法。


## 多态的作用
- 消除类型之间的耦合关系

## 主要的特点
- 多态是方法的多态，二不是属性的多态
- 多态存在的三个必要条件 
  - 要有继承；
  - 要有重写；
  - 父类引用指向子类对象。 
- 用该父类引用调用子类重写的方法


## 代码演示
- ```java
  public class TextPlay{
      public static void main(String[] args){
          Animal a = new Animal();
          animalCry(a);
          Dog d = new Dog();
      }

      static void animalCry(Animal a){
          a.shout();   //父类引用子类对象
      }
  }
  class Animal{
      public void shout(){
          System.out.println("叫");
      }
  }

  class Dog extends Animal{  //继承父类
      public void shout(){
          System.out.println("汪汪汪");//方法重写
      }
  }
  ```

## 多态的分类
 - **引用多态**
    - 父类的引用可以指向本类的对象
    - 父类的引用可以指向子类的对象
 - **方法多态**
    - 创建本类对象时，调用的方法为本类方法
    - 创建子类对象时，调用方法为子类重写的方法或者继承的方法  
  

## 对象的转换（ClassCastException）
 - 代码演示
    ```java
    Animal d = new Dog();//自动向上转型
    Dog d2 = (Dog)d;//强制向下转型
    //在Dog类中加上看门的方法，新建一个cat类，则
    animalCry(new Cat());
    Dog d2 = (Dog)d;
    Animal c = new Cat();
    Dog d3 = (Dog) c; //Cat强转Dog，编译未报错，但实际上不能转换
    d3.door();
    ```
 - 总而言之，子类转向父类没有风险，而父类转向子类会存在风险
 - 解决方法：我们可以使用`instance of`运算符，来解决引用对象的类型，避免类型转换的安全性问题
    - 例如：
    ```java
    Dog dog = new Dog();
    Animal animal = new Dog ;//向上类型转换
    if(Animal instance of Dog){
        Dog dog2 = (Dog)Animal;
    }else{
        System.out.println("无法进行转换");
    }

## 抽象类(abstract)
### 基本了解
 - **抽象类**，即只有方法声明，无方法体的一种类，它的出现避免了子类设计的随意性，并严格限制子类设计，为子类提供模板

### 语法
 - 在定义的类前使用`abstract`关键字修饰的即为抽象类
    ```java
    public abstract 类名(){

    }
    ```

### 作用
 - 限制规定子类必须实现某些方法，但不关注实现细节

### 使用规则
 - `abstract`定义抽象类
 - `abstract`定义抽象方法时，只是声明，而不需要实现
 - 包含抽象方法的类是抽象类
 - 抽象类可以包含普通方法，也可以没有抽象方法
 - 抽象类不能直接创建，可以定义引用变量                    

### 注意的点
1. 有抽象方法的类能定义抽象类
2. 抽象类不能实例化，并且不能用`new`来实例化抽象类
3. 抽象类可汗属性、方法、构造方法，但构造方法不能用来`new`实例，只能用来被子类调用
4. **抽象类只能用来被继承**
5. **抽象方法必须被子类实现**

## 接口(Interface)
### 概念
- 类是一种具体实现体，而接口定义了某一批类所需要遵守的规范，接口不关心这些类的内部数据，也不关心这些类里方法的实现细节，它值规定这些类里必须提供某些方法
- 接口的出现，实现了程序设计中设计与实现的分离，可以说是抽象类的延伸

### 基本语法
- 修饰符 `interface` 接口名 `extends` 父接口1，父接口2{

  }
    - 修饰符一般建议使用`public`，不能使用`private`和`protected`修饰接口
- 实际代码演示：
    ```java
    //方法必须公有化
    public interface flyable{
        void fly();//这里只能含有常量，抽象方法
    }
    class plane implements flyable{
        //可以实现一个或多个接口
        public void fly(){
            System.out.println("飞机飞起来了");
        }
    }
    ```
### 注意的点
- 接口在使用过程中，还经常与匿名内部类配合使用
- 匿名内部类就是没有名字的内部类
- 多用于关注实现而不关注实现类名称
- 接口支持多继承
- 接口的字段默认都是`static`和`final`                                

## 回调的实现（callback）
- 多态的扩展
- 可以指出某个特定事件发生时应该采取得到动作

## 内部类（Inner）
- 特点：
    - 只能让外部类直接访问，不可在同包中的其他类直接访问
    - 可访问外部类私有属性，但外部类不能访问内部类的内部属性
- 使用场景：
    - 只为所在外部类通过服务的情况下优先使用
- 分类
    - 成员内部类
        - 静态
        - 非静态
    - 匿名内部类（只用一次的类，也称局部内部类 ）

