# 組合語言CTF實戰.md
```
Pico CTF 2014 : Basic Asm
PicoCTF2018-assembly-0
1-4.林思辰_read-asm
1-5.林思辰_run-asm
```
## Pico CTF 2014 : Basic Asm
```
We found this program (snippet), but we're having some trouble figuring it out. 
What's the value of %eax when the last instruction (the NOP) runs?

Hint:
You may want to convert the assembly into some equivalent C code, which will be easier to read!
```
###  snippet.txt
```
# This file is in AT&T syntax - see http://www.imada.sdu.dk/Courses/DM18/Litteratur/IntelnATT.htm
# and http://en.wikipedia.org/wiki/X86_assembly_language#Syntax. Both gdb and objdump produce
# AT&T syntax by default.
MOV $10814,%ebx
MOV $2972,%eax
MOV $10017,%ecx
CMP %eax,%ebx
JL L1
JMP L2
L1:
IMUL %eax,%ebx
ADD %eax,%ebx
MOV %ebx,%eax
SUB %ecx,%eax
JMP L3
L2:
IMUL %eax,%ebx
SUB %eax,%ebx
MOV %ebx,%eax
ADD %ecx,%eax
L3:
NOP
```
### 解法1
```
https://ehsan.dev/pico2014/reverse_engineering/basic_asm.html
```
```
# AT&T syntax by default.
MOV $10814,%ebx  ===> ebx=10814
MOV $2972,%eax   ===> eax=2972
MOV $10017,%ecx  ===> ecx =10017
CMP %eax,%ebx   ===> 
JL L1
JMP L2
L1:
IMUL %eax,%ebx
ADD %eax,%ebx
MOV %ebx,%eax
SUB %ecx,%eax
JMP L3
L2:
IMUL %eax,%ebx
SUB %eax,%ebx
MOV %ebx,%eax
ADD %ecx,%eax
L3:
NOP
```
### 解法2
```
https://github.com/VulnHub/ctf-writeups/blob/master/2014/picoctf/basic-asm.md
```

```
[1]改寫程式 ==> 添加一行 basic.s 
.global main
.text

main:

MOV $119,%ebx
MOV $28557,%eax
MOV $8055,%ecx
CMP %eax,%ebx
JL L1 
JMP L2 
L1:
IMUL %eax,%ebx
ADD %eax,%ebx
MOV %ebx,%eax
SUB %ecx,%eax
JMP L3 
L2:
IMUL %eax,%ebx
SUB %eax,%ebx
MOV %ebx,%eax
ADD %ecx,%eax
L3:
INT3    # <--- set a breakpoint here
NOP

[2]編譯
gcc -g basic basic.s

[3]使用gdb
gdb ./basic -q -batch -n -ex 'r' -ex 'p $eax'
```
## PicoCTF2018-assembly-0
```
Reversing 150: assembly-0
Challenge

What does asm0(0xd8,0x7a) return? Submit the flag as a hexadecimal value (starting with 0x).

NOTE: Your submission for this question will NOT be in the normal flag format. 
Source located in the directory at /problems/assembly-0_1_fc43dbf0079fd5aab87236bf3bf4ac63.
```
```
.intel_syntax noprefix
.bits 32
	
.global asm0

asm0:
	push	ebp
	mov	ebp,esp
	mov	eax,DWORD PTR [ebp+0x8]
	mov	ebx,DWORD PTR [ebp+0xc]
	mov	eax,ebx
	mov	esp,ebp
	pop	ebp	
	ret
```

### Solution
```
.intel_syntax noprefix
.bits 32

.global asm0

asm0:
	push	ebp
	mov	ebp,esp
	mov	eax,DWORD PTR [ebp+0x8] ==>asm0(0xd8,0x7a)  
                                  DWORD PTR [ebp+0x8]==>0xd8  
                                  DWORD PTR [ebp+0xc]==>0x7a
	mov	ebx,DWORD PTR [ebp+0xc] ==>把DWORD PTR [ebp+0xc] 複製到 ebx
	mov	eax,ebx   ==>把ebx 複製到 eax
	mov	esp,ebp
	pop	ebp
	ret           ==> 回傳eax所存的值
  
we can deduce the output manually. ret will return the value of eax, 
which was set to the value of ebx (mov eax ebx), 
and ebx was set do the second argument we passed to the program (mov ebx,DWORD PTR [ebp+0xc]), 
which in this case was 0x7a

Flag ==> 0x7a
```


## 
```


```


## 
```


```



