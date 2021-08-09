


``` java
//  这是我的第一个java语言代码
public class App {
    public static void main(String[] args) throws Exception {
        System.out.println("Hello, World!");
    }
}
```

``` java


```

# JAVA Code Grammer


``` java
public static void main(String[] args) {
    // Coding there
}

```

JAVA关键字
import  goto  const  
if while for do
int float long short
null true false void return
public private protected
所有关键字都是小写英文


## 常量和变量


### 常量
常量，定义常量时进行初始化，名称通常用大写字母。
声明常量的语法为：`final [type] [name] = [value];`。

``` java
package constant;
public class FinalVar {
    static final float PRICE = 2.5F;
    public static void main(String[] args) {
        System.out.println("白菜的市场价格是："+PRICE+"元。");
    }
}
// 白菜的市场价格是：2.5元。
```


### 变量
变量，和C语言的类似。
声明常量的语法为：`[type] [name] = [value];`。
``` java
int t = 6;
char x, y, z;
byte a = 1, b = 2, c = 3;
```
成员变量`private`，作用范围为整个类，具有默认值：0、false、null。

局部变量，没有默认值，必须初始化。

静态变量（类变量）`static`，具有默认值，。
`static private`, `static public`

静态变量节省内存，成员变量更加灵活。

## 数据类型

basic data type: int, float, char, bool. 

reference data type: class, interface, array. 

基本类型 | 关键字 | 占用字节（1 byte = 8 bit） | 范围 |
 - | - | - | - |
字节 | byte | 1 byte | -128~127 |
短 | short | 2 byte | -32768~32767 |
整型 | int | 4 byte | ... |
长 | long | 8 byte | ... |
单精度浮点型 | float | 4 byte | ... |
双精度浮点型 | double | 8 byte | ... |
字符型 | char | 2 byte | 0~65536 |
布尔型 | boolean | 1 byte | true or false |


#### 整数型




#### 浮点型（实型）

type byte range
float 4 -3.4E+38~3.4E+38（6~7位有效小数位）
double 8 -1.7E+308~1.7E+308（15位有效小数位）

`float f1 = 36.24F, f2 = -5.848f, f3 = 9.12, f4;`
`double d1 = 124.44D, d2 = 243.12d, d3 = 23.45, d4;`


#### 字符型

type byte range
char 2 0~65536
`char c1 = 'A', c2 = 65; // Unicode`

#### 布尔型

boolean 1 true, false


#### 基本类型转换

自动类型转换（隐式转换）低精度向高精度，强制类型转换（显示转换）高精度向低精度。
`int x; double y; x = (int)y;`


## 运算符

#### 基本赋值运算符 =

#### 复合赋值运算符 += -= *=/= %= &= |= ^=


#### 算术运算符 + - * / %


#### 比较运算符 > < >= <= == !=


#### 条件运算符 ? :
Result = < expression > ? < statement1 > : < statement2 >


#### 逻辑运算符 && || !


#### 位运算符 & | ^ ~ << >> >>>


#### 自增自减运算符 ++ --



#### 运算符优先级

1 括号
2 一元运算符
3 算术运算符
4 关系运算符
5 逻辑运算符
6 条件、赋值运算符



## 流程控制

### 分支控制

#### if
``` java
if (boolean)
{
    // struct
}
```

``` java
if (boolean)
{

}else{

}
```

``` java
if (boolean)
{

}else if(boolean){

}else if(boolean){

}else{

}
```

#### switch
``` java
switch (){
    case value :
        // code
        break;
    case value :
        // code
    default : 
        // code
}
```

### 循环控制

#### for

#### while

#### do while 

### 跳转语句

#### break;

#### continue;

#### return;







## JAVA代码编写规范



### 命名规范



### 声明规范

### 语句规范

### 注释规范
注释
``` java
// 单行注释

/*
多行注释
*/

/**
文档注释
*/
```


### 编程规范

### 文件内容规范

### 缩进排版规范


# JAVA Code Mind

## 面向对象编程


Java is a fully object-oriented programming language. The foundation of object-oriented programming is the class. 

There are three main features of class, encapsulation, inheritance and polymorphism. 



``` java
package create; // 创建包[create]，Student类属于create包，
public class Student {
    // The properties of the class
    public String name;
    public int age;
    public String school;
    // 声明类的方法
    public void study(){
        System.out.println("我是："+name+"，今年"+age+"岁，在"+school"上学。");
    }
}
```





