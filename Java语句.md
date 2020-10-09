# Java语句

## Java 输入语句

### 1.1 使用Scanner类
- 步骤：
  - 使用`java.util`包，即```import java.util.*;```
  - 构造Scanner类对象，它属于标准输入流`System.in`
    - 即：
      ```java
      Scanner s = new Scanner(System.in);
      ```
  - 常用的`next()`方法系列：
    - `next()` &nbsp;输入字符串（以空格作为分隔符）
    - `nextInt()` &nbsp;输入整数
    - `nextLine()` &nbsp;输入字符串
    - `nextDouble()` &nbsp;输入双精度数

### 1.2 使用java.io.BufferReader和java.io.InputStreamReader
- 1. 导入io包
  ```java
  import java.io.*;
  ```
- 2. 构造`BufferReader`类对象
  ```java
  Bufferreader br = new BufferReader(new InputStreamReader)(System.in);
  ```

## Java输出语句
- 分类：
  - `System.out.println();`  换行打印
  - `System.out.print();` 不换行打印
  - `System.out.write(1121);` 字节输出 
  - `System.out.printf("%+8.3f\n",3.14);` 按格式输出

### 2.1 换行打印
- `System.out.println();` &nbsp;是最常见的输出语句，把（）里的内容转换为字符串输出，并且换行
  - 若输出的是一个基本数据类型，则转换为字符串
  - 若输出的是对象，则会自动调用对象的`toString();`方法

### 2.2 按格式输出
- `System.out.printf("%+8.3f\n",3.14);` &nbsp;通过格式化文本和参数列表输出


## Java条件语句
### 3.1 if语句
#### 3.1.1 最普通的写法：
  ```java
  if(条件表达式){
      条件执行的语句;
  } 
  ```
#### 3.1.2 `if....else`写法：
  ```java
  if(条件表达式){
      条件执行的语句;
  } else{
      执行语句;
  } 
  ```
#### 3.1.3 多重if
  ```java
  if(条件1){
      代码块1;
  }else if(条件2){
      代码块2;
  }else if(条件3){
      代码块3;
  }
  ```
#### 3.1.4 嵌套if
  ```java
  if(条件1){
      if(条件2){
          代码块1;
      }else{
          代码块2;
      }
  }else{
      代码块3;
  }
  ```
### 3.2 switch语句
- 语法：
  ```java
  switch(表达式){
      case 值1:
        执行的代码块1;
        break;
      case 值2:
        执行的代码块2;
        break;  
     default:
        默认的执行代码;   
  } 
  ```

### 3.3 while语句
#### 3.3.1 基本写法
    ```java
    while(判断条件){
        循环语句;
    }
    ```
   - 先判断，后执行
#### 3.3.2 do-while
    ```java
    do{
        循环语句;
    }while(判断条件);
    ```
  - 先执行，后判断

### 3.4 for语句
- 语法：
  ```java
  for(循环变量初始化;循环条件;循环变量变化){
      循环语句;
  } 
  ```
### 3.5 braek语句
- 语法：
  ```java
  if(条件){
      执行操作语句;
      break;//退出此循环，执行循环外的代码
  } 
  ```
### 3.6 continue语句
- 语法：
  ```java
  if(条件){
      执行操作;
      continue;//通过continue结束本次循环，进行下一次循环
  } 
  ```
