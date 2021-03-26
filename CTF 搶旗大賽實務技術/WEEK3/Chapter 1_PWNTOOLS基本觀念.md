# registers 暫存器
```
registers can be grouped into four categories:
[1]General purpose==>mathematical operations
       EAX, EBX, and ECX 
       ==>can be used to store data and addresses, 
          offset addresses, perform counting functions, and many other things.
          
       重要阿 ~~~the extended stack pointer register(ESP) 
                  simply the stack pointer. 
       ESP points to the memory address where the next stack operation 
       will take place. 
       In order to understand stack overflows in

[2]Segment ==>
      the segment registers are 16 bit (other registers are 32 bits in size). 
      Segment registers ==>  CS, DS, and SS, 
          ==>  are used to keep track of segments and 
                to allow backward compatibility with 16-bit applications.
                
[3]Control ==> control the function of the processor
           ==> Extended Instruction Pointer (EIP)
                            or simply the Instruction Pointer. 
           ==>  EIP contains the address of the next machine instruction 
                 to be executed. 
                 Naturally, if you want to control the execution path of a program, 
                 it is important to have the ability to access and change 
                 the value stored in the EIP register.

[4]Other ==>Extended Flags (EFLAGS) register
            which comprises many single-bit registers that are used to store the results of various tests 
            performed by the processor.
```
# Chapter 1 筆記
## Recognizing C and C++ Code Constructs in Assembly

C 語法
```
int number;
. . . more code . . .
number++;
```

組合語言如是說
```
number dw 0  ========>  use the Define Word (DW) instruction to define a value for our integer, number
. . .more code . . .
mov eax,number ========>   eax <---- number
inc eax        ========>   eax <---- eax + 1
mov number,eax  ========>   number <---- eax
```
##

C 語法
```
int number;

if (number<0)
{
. . .more code . . .
}
```

組合語言如是說
```
number dw 0
mov eax,number  ========>   eax <---- number
or eax,eax
jge label  ===> we jump to label if number is greater than or equal to zero with 
           ===> Jump if Greater than or Equal to (JGE).
<no>
label :<yes>

```
```
這三種指令有何差異?
test eax,eax
or eax,eax 
and eax,eax

https://stackoverflow.com/questions/23691989/difference-between-or-eax-eax-and-test-eax-eax
```
##

C 語法
```
int array[4];
. . .more code . . .
array[2]=9;
```

組合語言如是說
```
array dw 0,0,0,0  
. . .more code . . .
mov ebx,2
mov array[ebx],9

```

##

C 語法
```
int triangle (int width, in height){
  int array[5] = {0,1,2,3,4};
  int area;
  area = width * height/2;
  return (area);
}
```

組合語言如是說 ==> gdb 反組譯
```
0x8048430 <triangle>: push %ebp
0x8048431 <triangle+1>: mov %esp, %ebp
0x8048433 <triangle+3>: push %edi
0x8048434 <triangle+4>: push %esi
0x8048435 <triangle+5>: sub $0x30,%esp
0x8048438 <triangle+8>: lea 0xffffffd8(%ebp), %edi
0x804843b <triangle+11>: mov $0x8049508,%esi
0x8048440 <triangle+16>: cld
0x8048441 <triangle+17>: mov $0x30,%esp
0x8048446 <triangle+22>: repz movsl %ds:( %esi), %es:( %edi)
0x8048448 <triangle+24>: mov 0x8(%ebp),%eax
0x804844b <triangle+27>: mov %eax,%edx
0x804844d <triangle+29>: imul 0xc(%ebp),%edx
0x8048451 <triangle+33>: mov %edx,%eax
0x8048453 <triangle+35>: sar $0x1f,%eax
0x8048456 <triangle+38>: shr $0x1f,%eax
0x8048459 <triangle+41>: lea (%eax, %edx, 1), %eax
0x804845c <triangle+44>: sar %eax
0x804845e <triangle+46>: mov %eax,0xffffffd4(%ebp)
0x8048461 <triangle+49>: mov 0xffffffd4(%ebp),%eax
0x8048464 <triangle+52>: mov %eax,%eax
0x8048466 <triangle+54>: add $0x30,%esp
0x8048469 <triangle+57>: pop %esi
0x804846a <triangle+58>: pop %edi
0x804846b <triangle+59> pop %ebp
0x804846c <triangle+60>: ret

```
