# 数组(Array)

**数组**（Array）是**有序**的元素序列，用来存储固定大小的同类型元素，在内存中占一片连续的存储区。



## 声明

```java
//基本类型的数组声明
int[] arr1;
char[] arr2;
byte[] arr3;
short[] arr4;
//引用类型的数组声明
String[] arr5;
...
```



##  创建

```java
//基本类型的数组声明
int[] arr1;
char[] arr2;
byte[] arr3;
short[] arr4;
//引用类型的数组声明
String[] arr5;

//创建数组
arr1=new int[10];//指定数组的长度为10
arr5=new String[5];
```



## 声明并创建

```java
int[] a=new int[10];
String[] b=new String[5];
```



## 多维数组

多维数组可以看成是数组的数组，比如二维数组就是一个特殊的一维数组，其每一个元素都是一个一维数组。

```java
int[][] a=new int[5][3];
a[0][1];//多维数组的引用
```



## Java中的Arrays类

java.util.Arrays 类能方便地操作数组，它提供的所有方法都是静态的。

```java
public static int binarySearch(Object[] a, Object key)
//用二分查找算法在给定数组中搜索给定值的对象(Byte,Int,double等)。数组在调用前必须排序好的。如果查找值包含在数组中，则返回搜索键的索引
//否则返回 (-(插入点) - 1)
    
public static boolean equals(long[] a, long[] a2)
//如果两个数组包含相同数量的元素，并且两个数组中的所有相应元素对都是相等的，则认为这两个数组是相等的
    
public static void fill(int[] a, int val)
//将指定的 int 值分配给指定 int 型数组指定范围中的每个元素
    
public static void sort(Object[] a)
//对指定对象数组根据其元素的自然顺序进行升序排列
```

