#
```


```

## 1996 
```
Aleph One’s “Smashing the Stack for Fun and Profit.” 
Written in 1996 and published in Phrack magazine, 
the paper explained for the first time in a clear and concise manner how buffer
overflow vulnerabilities are possible and how they can be exploited. 

http://insecure.org/stf/smashstack.html.
https://inst.eecs.berkeley.edu/~cs161/fa08/papers/stack_smashing.pdf
```
## Buffers
```
A buffer ==>  a limited, contiguously allocated set of memory. 
             The most common buffer in C is an array.
             
             int array[5] = {1, 2, 3, 4, 5};        
```

```
#include <stdio.h>
#include <string.h>

int main ()
{
  int array[5] = {1, 2, 3, 4, 5};
  
  for(int i=0; i< 5; i++)
      {
        printf("array %d : address is %x and value is %d\n" ,i, &array[i] ,array[i]);
      }

    return 0;
}
```

```
gcc array.c -o array
root@kali:~# ./array 
array 0 : address is 5dc68440 and value is 1
array 1 : address is 5dc68444 and value is 2
array 2 : address is 5dc68448 and value is 3
array 3 : address is 5dc6844c and value is 4
array 4 : address is 5dc68450 and value is 5
```

# Stack overflows
```
no inherent bounds-checking exists on buffers in the C or C++ languages. 
the C language and its derivatives do not have a built-in function to 
ensure that data being copied into a buffer will not be larger than the buffer can hold.
```
### buffer Overflow 1
```
#include <stdio.h>
#include <string.h>

int main ()
{
  int array[5] = {1, 2, 3, 4, 5};

  printf("%d\n", array[5]);
  
  return 0;
}
```
```
root@kali:~# gcc bf1.c -o bf1
root@kali:~# ./bf1
32765
root@kali:~# ./bf1
32767
root@kali:~# ./bf1
32766
root@kali:~# ./bf1
32767
root@kali:~# ./bf1
32764
root@kali:~# ./bf1
32767
root@kali:~# ./bf1
32764
root@kali:~# ./bf1
32765
```
```
==> how easy it is to read past the end of a buffer; 
   C provides no built-in protection.
```

## 寫入的問題 bufferoverflow 2
```
#include <stdio.h>
#include <string.h>

int main () 
{
   int array[5];
   int i;

   for (i = 0; i <= 255; i++ )
   {
      array[i] = 10;
   }
   
   return 0;
}
```
```
root@kali:~# gedit bf2.c
root@kali:~# gcc bf2.c -o bf2
root@kali:~# ./bf2
Segmentation fault  <=======當 當 當 當
```
# The Stack <==> Buffer <==> Array
```
The boundary of the stack is defined by the extended stack pointer (ESP) register, 
which points to the top of the stack.

Stack 的運算指令: push(壓入) pop
ESP指向:
IA32 ==> ESP points to the last address used by the stack. 
In other implementations, it points to the first free address.第一個空著的位置
```

```
see 簡報
```

# Functions and the Stack
```
使用stack ==> Function call 函數呼叫

The stack’s primary purpose is to make the use of functions more efficient.

From a low-level perspective, a function alters the flow of control of a program,
so that an instruction or group of instructions can be executed independently
from the rest of the program. 

More important, when a function has completed executing its instructions, 
it returns control to the original function caller. 

This concept of functions is most efficiently implemented with the use of the stack.
```

## Ubuntu 16.04 LTS 
```
# include <stdio.h>

# include <string.h>

void function(int a, int b){
     int array[5];
}

int main()
{
  function(1,2);
  printf("This is where the return address pointsZ");
  return 0;
}
```
```
ksu@KSU-Ubuntu-1604-32:~$ gedit s1.c
ksu@KSU-Ubuntu-1604-32:~$ gcc -g  -mpreferred-stack-boundary=2 -ggdb s1.c -o s1
ksu@KSU-Ubuntu-1604-32:~$ ./s1
This is where the return address pointsZ
```
使用 gdb
```
gdb s1
GNU gdb (Ubuntu 7.11.1-0ubuntu1~16.5) 7.11.1
Copyright (C) 2016 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.  Type "show copying"
and "show warranty" for details.
This GDB was configured as "i686-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<http://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
<http://www.gnu.org/software/gdb/documentation/>.
For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from s1...done.
```
反組譯 main 函數
```
(gdb) disas main
Dump of assembler code for function main:
   0x08048490 <+0>:	push   %ebp
   0x08048491 <+1>:	mov    %esp,%ebp
   0x08048493 <+3>:	push   $0x2  ==> 參數傳遞2 function(1,2)
   0x08048495 <+5>:	push   $0x1   ==> 參數傳遞1 function(1,2)
   0x08048497 <+7>:	call   0x804846b <function> ==> 函數呼叫 function(1,2) 
                ==> pushes RET (EIP) onto the stack. 
                ==> call then transfers flow of execution to function, at address 0x804846b
   0x0804849c <+12>:	add    $0x8,%esp
   0x0804849f <+15>:	push   $0x8048540
   0x080484a4 <+20>:	call   0x8048330 <printf@plt> ====> 函數呼叫 printf()
   0x080484a9 <+25>:	add    $0x4,%esp
   0x080484ac <+28>:	mov    $0x0,%eax
   0x080484b1 <+33>:	leave  
   0x080484b2 <+34>:	ret    
End of assembler dump.
```
反組譯 function 函數
```
(gdb) disas function
Dump of assembler code for function function:
   0x0804846b <+0>:	push   %ebp ====>  function prolog : stores the current frame pointer, EBP, onto the stack
   0x0804846c <+1>:	mov    %esp,%ebp ====>  function prolog: copies the current stack pointer into EBP
   0x0804846e <+3>:	sub    $0x18,%esp ====> the prolog creates enough space on the stack for our local variable, array, at <function+3>.
                                            “array” is 5 * 4 bytes  in size (20 bytes), 
                                            but the stack allocates 0x18  bytes of stack space for our locals
   0x08048471 <+6>:	mov    %gs:0x14,%eax
   0x08048477 <+12>:	mov    %eax,-0x4(%ebp)
   0x0804847a <+15>:	xor    %eax,%eax
   0x0804847c <+17>:	nop
   0x0804847d <+18>:	mov    -0x4(%ebp),%eax
   0x08048480 <+21>:	xor    %gs:0x14,%eax
   0x08048487 <+28>:	je     0x804848e <function+35>
   0x08048489 <+30>:	call   0x8048340 <__stack_chk_fail@plt>
   0x0804848e <+35>:	leave  
   0x0804848f <+36>:	ret    
End of assembler dump.
(gdb) 

```

# Overflowing Buffers on the Stack
```
# include <stdio.h>
# include <string.h>

void return_input (void){ 
        char array[30]; 
        gets (array); 
        printf("%s\n", array); 
}

int main() { 
        return_input(); 
        return 0; 
}
```
```
ksu@KSU-Ubuntu-1604-32:~$ gedit s2.c
ksu@KSU-Ubuntu-1604-32:~$ gcc -g  -mpreferred-stack-boundary=2 -ggdb s2.c -o s2
s2.c: In function ‘return_input’:
s2.c:7:9: warning: implicit declaration of function ‘gets’ [-Wimplicit-function-declaration]
         gets (array); 
         ^
/tmp/ccBFasTQ.o: In function `return_input':
/home/ksu/s2.c:7: warning: the `gets' function is dangerous and should not be used.
ksu@KSU-Ubuntu-1604-32:~$ ./s2
AAAAA
AAAAA
```
```
ksu@KSU-Ubuntu-1604-32:~$ ./s2
AAAAAAAAAAAAAAAAAAAAAAAAAAAAAA
AAAAAAAAAAAAAAAAAAAAAAAAAAAAAA
ksu@KSU-Ubuntu-1604-32:~$ ./s2
AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA
AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA
*** stack smashing detected ***: ./s2 terminated
Aborted (core dumped)
```
```
ksu@KSU-Ubuntu-1604-32:~$ gdb s2
GNU gdb (Ubuntu 7.11.1-0ubuntu1~16.5) 7.11.1
Copyright (C) 2016 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.  Type "show copying"
and "show warranty" for details.
This GDB was configured as "i686-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<http://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
<http://www.gnu.org/software/gdb/documentation/>.
For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from s2...done.
(gdb) disas return_input
Dump of assembler code for function return_input:
   0x0804848b <+0>:	push   %ebp
   0x0804848c <+1>:	mov    %esp,%ebp
   0x0804848e <+3>:	sub    $0x24,%esp
   0x08048491 <+6>:	mov    %gs:0x14,%eax
   0x08048497 <+12>:	mov    %eax,-0x4(%ebp)
   0x0804849a <+15>:	xor    %eax,%eax
   0x0804849c <+17>:	lea    -0x22(%ebp),%eax
   0x0804849f <+20>:	push   %eax
   0x080484a0 <+21>:	call   0x8048340 <gets@plt>
   0x080484a5 <+26>:	add    $0x4,%esp
   0x080484a8 <+29>:	lea    -0x22(%ebp),%eax
   0x080484ab <+32>:	push   %eax
   0x080484ac <+33>:	call   0x8048360 <puts@plt>
   0x080484b1 <+38>:	add    $0x4,%esp
   0x080484b4 <+41>:	nop
   0x080484b5 <+42>:	mov    -0x4(%ebp),%eax
   0x080484b8 <+45>:	xor    %gs:0x14,%eax
   0x080484bf <+52>:	je     0x80484c6 <return_input+59>
   0x080484c1 <+54>:	call   0x8048350 <__stack_chk_fail@plt>
   0x080484c6 <+59>:	leave  
   0x080484c7 <+60>:	ret    
End of assembler dump.
(gdb) b 0x080484a0
Function "0x080484a0" not defined.
Make breakpoint pending on future shared library load? (y or [n]) y
Breakpoint 1 (0x080484a0) pending.
(gdb) b *0x080484a0
Breakpoint 2 at 0x80484a0: file s2.c, line 7.
(gdb) b *0x080484c7
Breakpoint 3 at 0x80484c7: file s2.c, line 10.
(gdb) r
Starting program: /home/ksu/s2 

Breakpoint 2, 0x080484a0 in return_input () at s2.c:7
7	        gets (array); 
(gdb) disas main
Dump of assembler code for function main:
   0x080484c8 <+0>:	push   %ebp
   0x080484c9 <+1>:	mov    %esp,%ebp
   0x080484cb <+3>:	call   0x804848b <return_input>
   0x080484d0 <+8>:	mov    $0x0,%eax
   0x080484d5 <+13>:	pop    %ebp
   0x080484d6 <+14>:	ret    
End of assembler dump.
(gdb) x/20x $esp
0xbfffef48:	0xbfffef4e	0x0804852b	0x00000001	0xbffff014
0xbfffef58:	0xbffff01c	0x08048501	0xb7fb83dc	0x0804821c
0xbfffef68:	0x080484e9	0xcc391200	0xbfffef78	0x080484d0
0xbfffef78:	0x00000000	0xb7e1d647	0x00000001	0xbffff014
0xbfffef88:	0xbffff01c	0x00000000	0x00000000	0x00000000
(gdb) c
Continuing.
AAAAAAAAAABBBBBBBBBBCCCCCCCCCCDDDDDDDDDD
AAAAAAAAAABBBBBBBBBBCCCCCCCCCCDDDDDDDDDD
*** stack smashing detected ***: /home/ksu/s2 terminated

Program received signal SIGABRT, Aborted.
0xb7fd9d05 in __kernel_vsyscall ()

```

# 要的是 控制 eip
```
controlling the path of execution, or basically, controlling
what gets loaded into EIP, the instruction pointer
```

```
The address will be written in the buffer and will overwrite EBP and RET with our
new value. When RET is read off the stack and placed into EIP, the instruction
at the address will be executed. This is how we will control execution.
```

# Using an Exploit to Get Root Privileges
```
You force it to execve
a shell that inherits its permissions.
```

```
ksu@KSU-Ubuntu-1604-32:~$ gedit sh1.c
ksu@KSU-Ubuntu-1604-32:~$ gcc -g sh1.c -o sh1
ksu@KSU-Ubuntu-1604-32:~$ ./sh1
ksu@KSU-Ubuntu-1604-32:~$ gcc -g -fno-stack-protector sh1.c -o sh1
ksu@KSU-Ubuntu-1604-32:~$ ./sh1
Segmentation fault (core dumped)
```


# Return to libc
###
```
int main()
{
}
```
```
ksu@KSU-Ubuntu-1604-32:~$ gcc -g  w1.c -o ww1
ksu@KSU-Ubuntu-1604-32:~$ gdb ww1
GNU gdb (Ubuntu 7.11.1-0ubuntu1~16.5) 7.11.1


(gdb) b main
Breakpoint 1 at 0x80483e3: file w1.c, line 3.
(gdb) r
Starting program: /home/ksu/ww1 

Breakpoint 1, main () at w1.c:3
3	}
(gdb) p system
$1 = {<text variable, no debug info>} 0xb7e3fdb0 <__libc_system>
(gdb) q
```
```
ksu@KSU-Ubuntu-1604-32:~$ gdb ww1
GNU gdb (Ubuntu 7.11.1-0ubuntu1~16.5) 7.11.1
Copyright (C) 2016 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
.........
(gdb) b main
Breakpoint 1 at 0x80483e3: file w1.c, line 3.
(gdb) r
Starting program: /home/ksu/ww1 

Breakpoint 1, main () at w1.c:3
3	}
(gdb) p exit
$1 = {<text variable, no debug info>} 0xb7e339e0 <__GI_exit>
```
