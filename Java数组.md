# Java数组
## 数组的基本使用
- 什么是数组？形如```int[]score ={79,9,2,45};```称作数组

### 1.1 声明数组
- 语法：
  - 数据类型 &nbsp;`[]`&nbsp;数组名 
  - 或者：数据类型 &nbsp;数组名[]
- 例如：
  ```java
  int[] scores;//最好采用这种写法
  double height[]; //不推荐这种写法
  ```
- **注意！**
  - **在声明数组的同时不能指定数组长度,以下为错误写法**
    ```java 
    int[] arr = new int[4]{95,16,77,25};
    ```
### 1.2 分配空间
- 语法：
  - 数组名 &nbsp; `=` &nbsp;数据类型`[`数组长度`]`

### 1.3 赋值
- 数组从0开始计算（一位数组按顺序排列数字）
  - 语法：
    ```java
    score[0] = 92;//score数组的一号元素的数值为92
    score[1] = 98;
    ```
## 使用循环操作打印Java数组
- 代码演示：
  ```java
  int[] scores ={88,82,99,86,95};
  for(int i =0;i<score.length;i++){
      System.out.println(scores[i]);
  } 
  ```
  - 数组名`.length`为获取数组的长度

## 使用Arrays类按顺序打印Java数组
- 首先导入`Arrays`类
  ```java
  import java.utol.Arrays;
  ```
- 然后排序
  ```java
  Arrays.sort(数组名);
  ```
- 整体演示
  ```java
  //定义一个整型数组
  int[] score ={75,88,91,64,73};
  //使用Arrays类的sort()方法对数组进行排序
  Arrays.sort(score);
  ```
## 将数组转换为字符串
- 语法：
  ```java
  Array.toString(数组名);
  ```
- 例如：
  ```java
  System.out.println(Array.toString(scores));
  ```

## 使用for-each遍历数组
- 语法：
  ```java
  for(元素类型 元素变量  : 遍历对象){
      执行的代码;
  }      
  ```
- 例如
  ```java  
  //对一维数组而言
  int arr[] = {2, 3, 1};
  for (int x : arr) { 
  System.out.println(x); //逐个输出数组元素的值 
  //对List数组来说
  //创建List并添加元素 
  List<String> list = new ArrayList<String>(); 
  list.add("1"); 
  list.add("3"); 
  list.add("4"); 
  //利用froeach语句输出集合元素 
  System.out.println("----2----froeach语句输出集合元素"); 
  for (String x : list) { 
  System.out.println(x); 
  } 
  ```

## Java中使用二维数组

1. 声明数组并分配空间
   - 数据类型 &nbsp;`[][]` 数组名 `=` `new` 数据类型 `[`行的个数`]``[`列的个数`]`;
   - 例如：
     ```java
     int [][] nums = new int[5][6];
     ```
2. 赋值
   - 数组名`[`行索引`]``[`列索引`]` = 值;
3. 处理数组
   


