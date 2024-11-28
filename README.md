1.汇编语言loop循环
DATAS SEGMENT
    ;此处输入数据段代码  
DATAS ENDS

STACKS SEGMENT
    ;此处输入堆栈段代码
STACKS ENDS

CODES SEGMENT
    ASSUME CS:CODES,DS:DATAS,SS:STACKS
START:
    mov ax,2
    mov cx,11
    s:          ;伪指令 循环
    add ax,ax
    loop s      ;loop英语表示循环依次乘2，
                  ;直到ax=1000，cx=0001
    INT 21H
CODES ENDS
    END START
2.c语言循环在masm中实现（等差数列求和）
#include<stdio.h>
int x=0
int sum=0
for(int i=1;i<=100;i++)
x++;
sum+=x
    DATAS SEGMENT
    ;此处输入数据段代码  
DATAS ENDS
STACKS SEGMENT
    ;此处输入堆栈段代码
STACKS ENDS
CODES SEGMENT
    ASSUME CS:CODES,DS:DATAS,SS:STACKS
START:
    mov ax,0
    mov bx,0
    mov cx,100
    s: 
    inc ax         ;伪指令 循环 ax++
    add bx,ax
    loop s      ;loop循环，在末行显示loop 0009后输入p 结束循环1~100次
                ;结果bx=13ba（十进制5050）
                
    INT 21H
CODES ENDS
    END START
    
