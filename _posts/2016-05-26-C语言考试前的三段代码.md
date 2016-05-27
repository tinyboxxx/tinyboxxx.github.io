---
layout: post
title: 考试前写的三段C语言代码
date: 2016-05-26
categories: blog
tags: [code]
description: 三段C语言代码
---

# 第一段

这段是算摄氏度华氏度的，目前指针有问题输出不了float

~~~
//
//
//  a.c
//
//  Created by Tinyboxxx on 2016/5/26.
//  Copyright © 2016年 Tinyboxxx. All rights reserved.
//

#include<stdio.h>
int main()
{
    int *pf,*ph;
    float fahr,celsius;
    
    pf=&fahr;
    ph=&celsius;
    
    printf("华氏温度 摄氏温度\n");
    
    for(*pf=0;*pf<=100;*pf=*pf+20)
    {
        *ph=(*pf-32)*5.0/9;
        printf("   %3d %10d\n",*pf,*ph);
        printf("   %3f %10f\n",fahr,celsius);
    }
    
}
~~~



# 第二段

~~~
//
//
//  b.c
//
//  Created by Tinyboxxx on 2016/5/26.
//  Copyright © 2016年 Tinyboxxx. All rights reserved.
//

#include<stdio.h>
int main()
{
    int *p1,*p2;
    int a,b,c;
    printf("Input integers: ");
    scanf("%d%d%d",&a,&b,&c);
    if(b<a)
        swap(&a,&b);
    if(c<b)
        swap(&b,&c);
    
    printf("After sorted: %d %d %d",a,b,c);
}

int swap(int *p1,int *p2)
{
    int p;
    p=*p1;
    *p1=*p2;
    *p2=p;
}
~~~

# 第三段

这段代码老师说是送分题，然而还是很难写。

~~~
// 
//
//  c.c
//
//  Created by Tinyboxxx on 2016/5/27.
// http://zhidao.baidu.com/question/1957657006575421180.html
//

#include<stdio.h>
#include<math.h>
int main()
{
 int isprime (int m);
 int a,i;
 printf("请输入一个偶数");
 scanf("%d",&a);
 for(i=2;i<=a/2;i++)
    if(isprime(i)&&isprime(a-i))
   printf("%d=%d+%d\n",a,i,a-i);
    return 0;
}
int isprime (int m) 
{
   int i,k;//不用定义n
   k=(int)sqrt(m);//是m不是n
   for(i=2;i<=k;i++)
    if(m%i==0) return 0;//找到因子的话直接返回0  //是m不是n
     return 1;//循环结束没有返回0的话则说明没有找到因子  那么该数位素数
}
~~~

