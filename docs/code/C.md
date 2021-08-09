---
title: "Welcome to C/C++"
author: [李峦]
date: "2021-04-19"
keywords: [C, C++]
header-center: "北京交通大学"
footer-center: "Beijing Jiaotong University"
...



``` c++
//  这是我的第一个C语言代码
#include <stdio.h>
int main()  //  这是主函数
{
    printf("Hello World\n");    //  写第一行字Hello World
    printf("Welcome to CPL World\n");   //  写第二行字Welcome to CPL World
    return 0;   //  主函数返回值
}
```


``` c++

```

``` c++

```

``` c++

```

# 语法


## 基本操作

main function
``` c++
int main()  //  这是主函数
{
    return 0;   //  主函数返回值
}
```


### 变量


基本类型：int, short, long, signed, unsigned, char, float, double, void. 
控制：if...else, switch...case...default, for, while, do...while, return, break, continue, goto. 

自定义类型：enum, struct, union, typedef. 

修饰词：const, static, extern, inline, restrict, volatile. 

运算符：+, -, *, /, %, ++, --, &, |, ~, ^, &&, ||, !, <, >, <=, >=, ==, !=, <<, >>, ., ->, ?:, sizeof. 

复合运算符 

预处理器：#include, #define, #undef,#if/#ifdef/#ifndef...#elif...#else...#endif, defined, #pragma,#error 

有极少数关键字有多种语义，例如static、void，算是麻烦一点。还有指针相关的类型和使用也算是比较麻烦点。其他都没有太复杂的东西。看着床头上832页、两寸厚的《C++ Templates》第二版，几乎只涉及几个C++关键字（template, typename, decltype, using），然后就会觉得上面的都太简单了。



变量

| 基本类型     | 关键字   | 占用字节 | 范围         |
| ------------ | -------- | -------- | ------------ |
| 整型         | int      | 4 byte   | -65537~65537 |
| 字符型       | char     | byte     |              |
| 单精度浮点型 | float    | byte     |              |
| 双精度浮点型 | double   | byte     |              |
| 短           | short    | byte     |              |
| 长           | long     | byte     |              |
| 有符号       | signed   | byte     |              |
| 无符号       | unsigned | byte     |              |
| 空           | void     | byte     |              |



``` c++

```

``` c++

```

``` c++

```


### 判断

``` c++
if () 
{

}
```

``` c++
if () 
{

} else {

}
```

``` c++
if ()
{

} else if () {

} else {

}
```




### 循环



``` c++
for (int i; i < N; i++) 
{
    printf("%d ", i);
}
```
``` c++
while(i < N)
{
    printf("%d ", i);
    i++;
}
```


``` c++
do {
    printf("%d ", i);
    i++;
} while(i < N)
```




## 指针


### 指针类型（int *）的存储过程和原理


3.1 指针类型的赋值规范


（1）第一种先定义后赋值

``` c++
int *p;
p = &a; // 变量p存放的a的地址
printf("p = %d\n",p); // p = 6618636
```

重点：先了解，指针类型，`int *p`,虽然是`*p`在一起写着，但是变量名叫`p`，类型为`int *`，也就是整型的指针类型，当你理清变量名和类型之后，你对指针的理解程度已经懂了大半了 。


（2）第二种定义赋值一步完成

``` c++
int *r = &a; // 存放的是a的地址
printf("r = %d\n",r); // p = 6618636
```

还有一种常用的错误赋值方法：`p = a;`。错误的操作，不能把一个具体的数字赋给指针（类型不匹配），一个指针类型，一个int类型



可以把存放一个int类型变量的地址赋给一个int *指针类型的变量。
'='左边是一个int *指针类型的变量 ，可以存放放置着int类型数值的地址。
'='右边是&a，a是int类型的变量数值5，&是取地址符，&a就是拿到int类型a的数值的地址。

总的来说，就是把a的那片空间，给了p一个钥匙，让p也可以对a的那片空间操作，这个已经属于指针操作了，后面我们会讲到。

由上述可以证明，c语言的赋值，必须是类型对应

总结：int *p; 变量名叫p，类型为int *,可存放一个int数据的地址 。
注意：这块的可存放一个int数据的地址，不是存放一个地址，是int类型

例如：
``` c++
int a = 5;
int *p;
p = &a;
```
这里a是一个int类型的变量，存放的int类型的数值5，&a 取到了存放int类型a的地址。

`p = &a;` 把int类型a的地址赋给了int *类型的p，即就是int *类型的变量可存放一个int数据的地址。



``` c++
int *p; //
int **q; //
int ***m; //
```

## 结构体
结构体的声明语法如下

``` c++
struct [structure tag] /*结构体的标签*/{

   member definition; /*零个或多个成员变量的定义*/
   member definition;
   ...
   member definition;
} [one or more structure variables];  /*一个或多个结构体变量的定义*/
```

结构体标签(structure tag)是可选的，但是推荐还是写上，这样使得代码更加规范清晰，成员变量的定义一般为基本数据类型，如 int age; char name[10]等，成员变量之间使用;隔开,最后一个成员变量后面的;可选, 

如下面定义一个图书信息的结构体变量
``` c++
struct Books {
   char  title[50];
   char  author[50];
   char  subject[100];
   int   book_id;
} book;
```

``` c++
#include <stdio.h>
#include <string.h>

struct Books {
   char  title[50];
   char  author[50];
   char  subject[100];
   int   book_id;
};

int main( ) {
    
   struct Books Book1; /* Declare Book1 of type Book */
   struct Books Book2; /* Declare Book2 of type Book */
   
   /* book 1 specification */
   strcpy( Book1.title, "C Programming");
   strcpy( Book1.author, "Nuha Ali");
   strcpy( Book1.subject, "C Programming Tutorial");
   Book1.book_id = 6495407;

   /* book 2 specification */
   strcpy( Book2.title, "Telecom Billing");
   strcpy( Book2.author, "Zara Ali");
   strcpy( Book2.subject, "Telecom Billing Tutorial");
   Book2.book_id = 6495700;

   /* print Book1 info */
   printf( "Book 1 title : %s\n", Book1.title);
   printf( "Book 1 author : %s\n", Book1.author);
   printf( "Book 1 subject : %s\n", Book1.subject);
   printf( "Book 1 book_id : %d\n", Book1.book_id);

   /* print Book2 info */
   printf( "Book 2 title : %s\n", Book2.title);
   printf( "Book 2 author : %s\n", Book2.author);
   printf( "Book 2 subject : %s\n", Book2.subject);
   printf( "Book 2 book_id : %d\n", Book2.book_id);

   return 0;
}
// 输出以下结果
/* 
Book 1 title : C Programming
Book 1 author : Nuha Ali
Book 1 subject : C Programming Tutorial
Book 1 book_id : 6495407
Book 2 title : Telecom Billing
Book 2 author : Zara Ali
Book 2 subject : Telecom Billing Tutorial
Book 2 book_id : 6495700
*/
```

``` c++

```

结构体指针

结构体数组

结构体的内存计算


## 常用函数







# 数据结构












# 算法


## Sort

**比较类排序**：通过比较来决定元素间的相对次序，由于其时间复杂度不能突破O(nlogn)，因此也称为非线性时间比较类排序。
交换排序（冒泡排序、快速排序）、插入排序（简单插入排序、希尔排序）、选择排序（简单选择排序、堆排序）、归并排序（二路归并排序、多路归并排序）。

**非比较排序**：不通过比较来决定元素间的相对次序，它可以突破基于比较排序的时间下界，以线性时间运行，因此也称为线性时间非比较类排序。
计数排序、桶排序、基数排序。


``` c++
void SelectSort(int arr[], int n)
{
	/*	int k;		//指向最小元素下标
		for (int i = 0; i < n - 1; i++)
		{
			k = i;	//初始指向0，每次排序后i加一
			for (int j = i + 1; j < n; j++)
			{
				if (arr[k]>arr[j])
				{
					k = j;	//将最小元素下标赋值给k
				}
			}
			swap(arr, k, i);
		}
	*/
	for (int i = 0; i < n - 1; i++)
	{
		for (int j = i + 1; j < n; j++)
		{
			if (arr[i] > arr[j])
			{
				swap(arr, i, j);
			}
		}
	}
}
```

``` c++
void swap(int arr[], int x, int y)
{
	int temp = arr[x];
	arr[x] = arr[y];
	arr[y] = temp;
}
```

``` c++
void show(int arr[], int n)
{
	for (int i = 0; i < n; i++)
	{
		printf("%d\t", arr[i]);
	}
	printf("\n");
}
```

``` c++
void _merge_in_arr(int arr[], int left, int mid, int right)
{
	int length = right - left + 1;					//定义一个辅助的空间的长度
	int *pData = (int*)malloc(sizeof(int)*length);//分配一个动态内存来调整元素的位置
	memset(pData, 0, sizeof(int)* length);

	//合并
	int low = left;		//左边区间的起始下标
	int hig = mid + 1;	//右边区间的起始下标
	int index = 0;		//辅助数组的下标

	while (hig <= right)//右区间没有合并完
	{
		while (low <= mid && arr[low] <= arr[hig])//证明左区间没有合并完，且左区间的值小于右区间的值
		{
			pData[index] = arr[low];			//把左边的值放进辅助数组
			low++;								//左边往高位移，下一次需要判断左边的新下标
			index++;							//下一次放进辅助数组的新下标
		}
		if (low > mid)	//证明左区间已经放完
			break;

		while (hig <= right && arr[low] > arr[hig])//证明右区间没有合并完，且左区间的值大于右区间的值
		{
			pData[index] = arr[hig];			//把右边的值放进辅助数组
			hig++;								//右边往高位移，下一次需要判断右边的新下标
			index++;							//下一次放进辅助数组的新下标
		}
	}

	//到这一步，证明起码有一个区间已经合并完成
	if (hig <= right)	//证明右边没有完成
		memmove(&pData[index], &arr[hig], sizeof(int)* (right - hig + 1));
	if (low <= mid)		//证明左边没有完成
		memmove(&pData[index], &arr[low], sizeof(int)* (mid - low + 1));

	//把所有区间都合并到了辅助区间
	memmove(&arr[left], pData, sizeof(int)* length);
	free(pData);	//释放空间
}

void radix_sort(int arr[], size_t len)
{
	int**temp = (int **)malloc(sizeof(int) * 10);	//10行
	//申请动态内存   辅助数组temp[10][];
	for (int i = 0; i < 10; i++)
	{
		temp[i] = (int *)malloc(sizeof(int)*len);
	}

	for (int i = 1; i <= 100; i *= 10)//循环数值可能有的位数
	{
		for (int x = 0; x < 10; ++x)//辅助数组行循环
		{
			for (int y = 0; y < len; ++y)//辅助数组列循环
			{
				temp[x][y] = -1;//辅助数组的初始化赋值，-1表示在arr里面不可能出现的数值 
			}
		}
		//arr数组中的元素放入辅助数组
		for (int m = 0; m < len; ++m)
		{
			int index = (arr[m] / i) % 10;
			temp[index][m] = arr[m];
		}
		//把辅助数组的内容放回待排序数组
		int k = 0;//待排序的下标
		for (int x = 0; x < 10; x++)
		{
			for (int y = 0; y < len; ++y)
			{
				if (temp[x][y] != -1)
					arr[k++] = temp[x][y];
			}
		}
	}
	//释放内存
	for (int i = 0; i < 10; i++)
	{
		free(temp[i]);
	}
	free(temp);
}
```

``` c++
void MergeSort(int arr[], int left, int right)
{
	if (left >= right)//递归的终止条件，left == right证明这个区间只有一个元素，不需要再拆了
		return;
	int mid = ((right - left) >> 1) + left;//求中点
	MergeSort(arr, left, mid);		//拆分左
	MergeSort(arr, mid + 1, right);	//拆分右
	//并操作
	_merge_in_arr(arr, left, mid, right);
}
```

``` c++

```


``` c++
void QuickSort(int arr[], int left, int right)
{
	if (left >= right) return;//只有一个元素不排
	int i = left, j = right;
	while (i < j)
	{
		while (i < j&&arr[j] >= arr[left])	//从右向左找第一个小于arr[left]的数
			--j;
		while (i < j&&arr[i] < arr[left])	//从左向右找第一个大于等于arr[left]的数
			++i;
		if (i < j)
			swap(arr, i, j);
	}
	QuickSort(arr, left, i - 1);//排左边
	QuickSort(arr, i + 1, right);//排右边
}
```

``` c++
void ShellSort(int arr[], int n)
{
	int tempVal, j;
	int jump = n >> 2;			//步长值
	while (jump != 0)
	{
		for (int i = jump; i < n; i++)
		{
			tempVal = arr[i];	//保存待排序的第一个数，也就是待插入的数
			for (j = i - jump; j >= 0 && tempVal < arr[j]; j -= jump)
			{
				arr[j + jump] = arr[j];
			}
			arr[j + jump] = tempVal;
		}
		jump = jump >> 1;		//步长值减半
	}
}
```

``` c++
void InsertSort(int arr[], int n)
{
	int tempVal;
	for (int i = 1, j; i < n; i++)
	{
		tempVal = arr[i];	//保存要插入的值
		for (j = i - 1; tempVal < arr[j] && j >= 0; --j)	//数据往后移动，给要插入的值腾位
		{
			arr[j + 1] = arr[j];
		}
		arr[j + 1] = tempVal;	//插入数据
	}
}
```

``` c++
void BubbleSort(int arr[], int n)
{
	//从小到大排序 相邻来两个数比较，将大的数字往后放
	for (int i = 0; i < n - 1; i++)			//n-1是因为数组下标最大为n-1 要进行10轮比较
	{
		//n-1是因为数组下标最大为n-1 要进行10次比较，再减i是因为每最后的i个元素已经有序不需要继续排序
		for (int j = 0; j < n - 1 - i; j++)
		{
			if (arr[j] > arr[j + 1])			//两两比较，将小的数据放前面
			{
				swap(arr, j + 1, j);
			}
		}
	}
}
```

``` c++

```

``` c++

```

``` c++

```

``` c++

```
## Search


1. 顺序查找
2. 二分查找
3. 插值查找
4. 斐波那契查找
5. 分块查找
6. 树表查找
7. 哈希查找

顺序查找
基本思想：顺序查找也称为线形查找，属于无序查找算法。


``` c++
int length = arr.Length;
            for (int i = 0; i < length; i++)
            {
                if(arr[i] == value)
                {
                    return i;
                }
            }
            return -1;
```

二分查找
基本思想：元素必须是有序的，属于有序查找算法。注：折半查找的前提条件是需要有序表顺序存储，对于静态查找表，一次排序后不再变化，折半查找能得到不错的效率。但对于需要频繁执行插入或删除操作的数据集来说，维护有序的排序会带来不小的工作量，那就不建议使用。——《大话数据结构》

``` c++

```

``` c++

```

``` c++

```

``` c++

```

``` c++

```

``` c++

```

``` c++

```

``` c++

```

``` c++

```

``` c++

```

``` c++

```



# 例程


``` c++

```

``` c++

```

``` c++

```

``` c++

```

``` c++

```

``` c++

```