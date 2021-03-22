#
```


```
# Program 4.1 Addition and Subtractio 4.2.2 加法與減法

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
