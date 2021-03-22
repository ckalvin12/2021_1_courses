# 第4章 基本指令Basic Instructions
```
4.1 簡介
4.2 數據的移動與算術運算
4.2.1 移動數據
4.2.2 加法與減法
4.2.3 乘法與除法
4.2.4 移位
4.2.5 處理負值

4.3 數據的尋址與傳輸
4.3.1 數據對齊
4.3.2 數據尋址
4.3.3 數組 ARRAY 陣列
4.3.4 改變數據的大小及類型

```
# Program 4.1 Addition and Subtractio 
```
4.2.2 加法與減法
```
## x86/Program_4.1_GAS_Linux.s
```
.data
sum: .long 0
val: .long 25

.text
.globl _main
_main:

movl $0, %eax  ==> %eax =0
incl %eax      ==> %eax =1
addl $200, %eax ==> %eax =1 +200 = 201
subl val, %eax  ==> %eax = 201-25 =176
movl %eax, sum  ==> sum =175
decl sum        ==> sum =174 
negl sum        ==> sum =-174 

movl $1, %eax
movl $0, %ebx
int $0x80
.end
```
## x86_64/Program_4.1_GAS_Linux.s
```
.data
sum: .quad 0
val: .quad 25

.text
.global _main
_main:

mov $0, %rax
inc %rax
add $200, %rax
sub val(%rip), %rax
mov %rax, sum(%rip)
dec sum(%rip)
neg sum(%rip)

movq $60, %rax
xorq %rdi, %rdi
syscall
.end
```
## x86/Program_4.1_NASM.asm
```
SECTION .data
sum: DD 0
val: DD 25

SECTION .text
global _main
_main:

mov eax, 0
inc eax
add eax, 200
sub eax, [val]
mov [sum], eax
dec DWORD [sum]
neg DWORD [sum]

mov eax, 1
mov ebx, 0
int 80h
```
## x86_64/Program_4.1_NASM.asm
```
SECTION .data 
sum: DQ 0
val: DQ 25

SECTION .text 
global _main
_main:

mov rax, 0 
inc rax
add rax, 200 
sub rax, [val] 
mov [sum], rax 
dec QWORD [sum] 
neg QWORD [sum]

mov rax, 60
xor rdi, rdi
syscall
```

# Program 4.2 ultiplication(乘法) and Division(除法)

## x86/Program_4.2_GAS_Linux.s
```
.data
mval: .long 664751
dval: .long 8

.text
.globl _main
_main:

# MUL 1-op
movl mval, %eax
movl $8, %ebx
mull %ebx

# IMUL 1-op
movl mval, %eax
movl $8, %ebx
imull %ebx

# IMUL 2-op
movl $8, %eax
imull mval, %eax

# IMUL 3-op
imull $8, mval, %eax

# DIV 1-op
movl $0, %edx
movl $5318008, %eax
movl dval, %ecx
divl %ecx

# IDIV 1-op
movl $0, %edx
movl $5318008, %eax
movl dval, %ecx
idivl %ecx

movl $1, %eax
movl $0, %ebx
int $0x80
.end
```
## x86_64/Program_4.2_GAS_Linux.s
```
.data
mval: .quad 664751
dval: .quad 8

.text
.global _main
_main:

# MUL 1-op
mov mval(%rip), %rax
mov $8, %rbx
mul %rbx

# IMUL 1-op
mov mval(%rip), %rax
mov $8, %rbx
imul %rbx

# IMUL 2-op
mov $8, %rax
imul mval(%rip), %rax

# IMUL 3-op
imul $8, mval(%rip), %rax

# DIV 1-op
mov $0, %rdx
mov $5318008, %rax
mov dval(%rip), %rcx
div %rcx

# IDIV 1-op
mov $0, %rdx
mov $5318008, %rax
mov dval(%rip), %rcx
idiv %rcx

mov $60, %rax
xor %rdi, %rdi
syscall
.end
```

## x86/Program_4.2_NASM.asm
```
SECTION .data
mval: DD 664751
dval: DD 8

SECTION .text
global _main
_main:

; MUL 1-op
mov eax, [mval]
mov ebx, 8
mul ebx

; IMUL 1-op
mov eax, [mval]
mov ebx, 8
imul ebx

; IMUL 2-op
mov eax, 8
imul eax, [mval]

; IMUL 3-op
imul eax, [mval], 8

; DIV 1-op
mov edx, 0
mov eax, 5318008
mov ecx, [dval]
div ecx

; IDIV 1-op
mov edx, 0
mov eax, 5318008
mov ecx, [dval]
idiv ecx

mov eax, 1
mov ebx, 0
int 80h
```
## x86_64/Program_4.2_NASM.asm
```
SECTION .data 
mval: DQ 664751
dval: DQ 8

SECTION .text 
global _main
_main:

; MUL 1-op
mov rax, [mval] 
mov rbx, 8
mul rbx

; IMUL 1-op
mov rax, [mval] 
mov rbx, 8
imul rbx

; IMUL 2-op
mov rax, 8
imul rax, [mval]

; IMUL 3-op
imul rax, [mval], 8

; DIV 1-op
mov rdx, 0
mov rax, 5318008 
mov rcx, [dval] 
div rcx

; IDIV 1-op
mov rdx, 0
mov rax, 5318008 
mov rcx, [dval] 
idiv rcx

mov rax, 60
xor rdi, rdi
syscall
```
# Program 4.3 Negative Division 

# 4.3.2 資料定址
```
直接定址(direct addressing) ==> 直接使用由該識別字所代表的內存位址上的資料

間接定址(indirect addressing) 
==> 不直接使用某個記憶體位址上的資料，
    而是把該資料也當成位址來確定另外一個記憶體位置，轉而使用那個位置上的資料

NASM 的變數表示的就是其記憶體位址，而不是該位址中的值
（如果想使用這個值，要用方括號括起來，例如[sum] ）

編譯器 獲取變數的地址(address)

GAS ==> MOVS $M, M/%R
   範例:將32 位元變數sum 的記憶體位址保存到 esi 寄存器
        MOVL $sum, %esi
        
NASM ==> MDV SIZE [M]/R, M
       範例:將變數的記憶體位址保存到另一個變數
         MOV DWORD [sumaddr], sum
```
# Program 4.4 Array 陣列

## x86/Program_4.4_GAS_Linux.s
```
.data
array: .long 1, 2, 3, 4

.text
.globl _main
_main:

# Load using byte offsets
leal array, %esi
movl (%esi), %eax
movl 4(%esi), %ebx

# Save using indices
movl $2, %edx
movl $10, (%esi, %edx, 4)
movl $3, %edx
movl $20, (%esi, %edx, 4)

movl $1, %eax
movl $0, %ebx
int $0x80
.end
```

## x86_64/Program_4.4_GAS_Linux.s
```
.data
array: .quad 1, 2, 3, 4

.text
.global _main
_main:

# Load using byte offsets
leaq array(%rip), %rsi
movq (%rsi), %rax
movq 8(%rsi), %rbx

# Save using indices
movq $2, %rdx
movq $10, (%rsi, %rdx, 8)
movq $3, %rdx
movq $20, (%rsi, %rdx, 8)

movq $60, %rax
xorq %rdi, %rdi
syscall
.end
```

## x86/Program_4.4_NASM.asm
```
SECTION .data
array: DD 1, 2, 3, 4

SECTION .text
global _main
_main:

; Load using byte offsets
mov eax, [array]
mov ebx, [array + 4]

; Save using indices
mov edx, 2
mov DWORD [array + edx * 4], 10
mov edx, 3
mov DWORD [array + edx * 4], 20

mov eax, 1
mov ebx, 0
int 80h
```

## x86_64/Program_4.4_NASM.asm
```
SECTION .data
array: DQ 1, 2, 3, 4

SECTION .text 
global _main
_main:

; Load using byte offsets
lea rsi, [array]
mov rax, [rsi]
mov rbx, [rsi + 8]

; Save using indices 
mov rdx, 2
mov QWORD [array+rdx*8], 10 
mov rdx, 3
mov QWORD [array+rdx*8], 20

mov rax, 60
xor rdi, rdi
syscall

```

