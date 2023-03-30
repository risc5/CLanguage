### C Language
>This Article Is about The C Programe Language


* Char Point

```c
char *p = "abc";
printf(p); /* If p is untrusted, bad things will happen, otherwise the string p is written. */
printf("%c", *p); /* print the first byte in the string p */
printf("%s", p); /* print the string p */

```

 




- Normal variable stores the value whereas pointer variable stores the address of the variable.
- The content of the C pointer always be a whole number i.e. address.
- Always C pointer is initialized to null, i.e. int *p = null.
- The value of null pointer is 0.

- & symbol is used to get the address of the variable.
- \* symbol is used to get the value of the variable that the pointer is pointing to.
- If a pointer in C is assigned to NULL, it means it is pointing to nothing.
- Two pointers can be subtracted to know how many elements are available between these two pointers.

- But, Pointer addition, multiplication, division are not allowed.
- The size of any pointer is 2 byte (for 16 bit compiler).



~~~c
#include <stdio.h>
int main()
{
   int *ptr, q;
   q = 50;
   /* address of q is assigned to ptr */
   ptr = &q;
   /* display q's value using ptr variable */
   printf("%d", *ptr);
   return 0;
}
~~~







~~~shell
#include<stdio.h>
void main()
{ 
    char name[]="siva";
    int i;
    for(i=0;i<4;i++)
    {
        printf("%c",*(name+i));
    }
} 
~~~





Pointer（指示器，指针好像翻译的怪怪的）的本质是一块内存，指向memory的地址空间去，内存空间在物理上可连续也可以不连续，虚拟地址上是连续的。Pointer本身相当于门牌号（指示器），Pointer指向的房子，房子里面可以存放东西/具体数据。包涵两个部分，一部分是本身的门牌号，另外一部分是房子里的物品。



Array与Pointer有类似的功能，在解释器上可以相互转换，从底层来说本质上是一样的。

https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/

操作符(也叫做运算符)是对一个(*unary*)、两个(binary)或三个(ternary)



* **val** == **&val[0]**



```
// pointer to an array of five numbers
 int (* ptr)[5] = NULL;   
```

[**Pointer to an array**](https://www.geeksforgeeks.org/pointer-array-array-pointer/): [Pointer to an array](https://www.geeksforgeeks.org/pointer-array-array-pointer/) is also known as **[array pointer](https://www.geeksforgeeks.org/pointer-array-array-pointer/)**. We are using the pointer to access the components of the array.

```
// pointer to an array of five numbers
 int (* ptr)[5] = NULL;  
 
 
 
 
 //这个是多维度的东西
 
 
 // C program to print elements of a 2-D array
// by scripting a pointer to an array
#include<stdio.h>
 
int main()
{
  int arr[3][4] = {
                    {10, 11, 12, 13},
                    {20, 21, 22, 23},
                    {30, 31, 32, 33}
                  };
  int (*ptr)[4];
  ptr = arr;
  printf("%p %p %p\n", ptr, ptr + 1, ptr + 2);
  printf("%p %p %p\n", *ptr, *(ptr + 1), *(ptr + 2));
  printf("%d %d %d\n", **ptr, *(*(ptr + 1) + 2), *(*(ptr + 2) + 3));
  printf("%d %d %d\n", ptr[0][0], ptr[1][2], ptr[2][3]);
  return 0;
}

```

https://www.geeksforgeeks.org/pointer-array-array-pointer/



[**Array of pointers**](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/): “[Array of pointers](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/)” is an array of the [pointer variables](https://www.geeksforgeeks.org/pointers-c-examples/). It is also known as **pointer arrays**.  



~~~shell
// Declaration of an array of pointers:
int *ptr[3];
~~~

~~~shell


Declaration of an array of pointers:

 int *ptr[3];
We can make separate pointer variables which can point to the different values or we can make one integer array of pointers that can point to all the values. Example: 


// C++ program to demonstrate
// example of array of pointers.
 
#include <iostream>
using namespace std;
 
const int SIZE = 3;
 
int main()
{
 
    // creating an array
    int arr[] = { 1, 2, 3 };
 
    // we can make an integer pointer array to
    // storing the address of array elements
    int i, *ptr[SIZE];
 
    for (i = 0; i < SIZE; i++) {
 
        // assigning the address of integer.
        ptr[i] = &arr[i];
    }
 
    // printing values using pointer
    for (i = 0; i < SIZE; i++) {
 
        cout << "Value of arr[" << i << "] = " << *ptr[i] << endl;
    }
}
 
// This code is contributed by sarajadhav12052009
Output:
Value of arr[0] = 1
Value of arr[1] = 2
Value of arr[2] = 3


~~~

~~~shell
#include <stdio.h>
 
const int size = 4;
 
void main()
{
 
    // array of pointers to a character
    // to store a list of strings
    //本质上是数组，数组里面的类型是char* ,char* 说白了是修饰[]里面的元素的！
    //这个是单维度的东西
    char* names[] = {
        "amit",
        "amar",
        "ankit",
        "akhil"
    };
 
    int i = 0;
 
    for (i = 0; i < size; i++) {
        printf("%s\n", names[i]);
    }
}
~~~











###Ref
* https://github.com/risc5/CLanguage/blob/main/c.md




### Debug Tool
* Valgrind, Address Sanitizer, Coverity
* https://www.elinux.org/images/6/60/GDB-Anderson-ELC.pdf
