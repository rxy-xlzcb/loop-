# loop-
汇编语言loop循环
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
