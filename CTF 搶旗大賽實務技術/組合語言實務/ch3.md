#
```
http://www.ece.ualberta.ca/~cmpe490/documents/axiom/GNU_Assembler
```
# 1.題目 program 3.1
```
首先定義一個32 位元的變數sum，然後將兩個數字相加25+50，最後把運算結果保存到該變數sum中。
```
```
#include <stdio.h>

int main(){
  int sum =0 ;
  
  sum  = 25+50;
  
  return 0;
}
```
#  GAS, Clang/LLVM on Linux (32-bit)
```
組合語言的保留字不區分大小寫

識別字是由程式師所定義的名稱，用來表示變數、常數及過程等事物，
最多可以包含247 個字元
第一個字元不能是數位，且必須從英文字母（大寫的A 至z 及小寫的a 至z) 、底線（＿）、
問號(?)、at 符號(@)及美元符號($)這五種中選擇
其後的字元則可以使用數字。


Assembler directives are instructions to the assembler to perform various bookkeeping tasks, 
storage reservation, and other control functions. 
```

```
.data   ============>有初始化的變數 long sum = 0
sum: .long 0

.text  ============> 程式區
.globl _main
_main:  ============> 程式入口
movl $25, %eax
movl $50, %ebx
addl %ebx, %eax ============> 把 %ebx的值加上 %eax的值 再將結果存入 %eax
movl %eax, sum ============>把%eax的值 複製給sum 

movl $1, %eax 
movl $0, %ebx
int $0x80 ============>呼叫系統中斷 結束程式
.end
```
# GAS, Clang/LLVM on Linux (64-bit)
```
.data
sum: .quad 0

.text
.global _main
_main:
mov $25, %rax
mov $50, %rbx
add %rbx, %rax
mov %rax, sum(%rip)

mov $60, %rax
xor %rdi, %rdi
syscall
.end
```
# Sample Assembly Program - NASM (32-bit)
```
SECTION .data ============>有初始化的變數 long sum = 0
sum: DD 0  ============>

SECTION .text  ============> 程式區
global _main
_main:
mov eax, 25   ============>  eax<--25 
mov ebx, 50   ============>  ebx<--50 
add eax, ebx  ============>  eax<--25 +50 
mov DWORD [sum], eax

mov eax, 1  ============>  eax <-- 1
mov ebx, 0  ============>  ebx <-- 0 
int 80h     ============>呼叫系統中斷 結束程式
```
# Sample Assembly Program - NASM (64-bit)
```
SECTION .data 
sum: DQ 0

SECTION .text
global _main
_main:
mov rax, 25
mov rbx, 50 
add rax, rbx
mov QWORD [sum], rax

mov rax, 60
xor rdi, rdi
syscall
```
# Program 3.2
##  GAS, Clang/LLVM on Linux (32-bit)
```
.data                             # Section for variable definitions

decimalLiteral:    .byte 31       # Variable storing 31
hexLiteral:        .long 0xF      # Variable storing F (15 in decimal)
charLiteral:       .byte 'A'      # Variable storing 65 in decimal

# Variable containing a string that has a line break and is null-terminated
stringLiteral:     .ascii "This string has\na line break in it.\0"

# Variable that calculates the value of an expression to determine the
# length, in bytes, of the variable "stringLiteral" by subtracting the
# starting memory address of the variable from the current memory address
.equ lenString, (. - stringLiteral)

.bss                              # Section for uninitialized variables
.lcomm unInitVariable, 4          # Uninitialized, 4-byte variable

.text                             # Section for instructions
.globl _main                      # Make the label "_main"
                                  # available to the linker as an
                                  # entry point for the program
_main:                            # Label for program entry

# Label and instruction on
# the same line below
partOne: movl $10, %eax           # Assign 10 to the eax register
addl hexLiteral, %eax             # Add the value in hexLiteral to
                                  # the contents of the eax register
                                  # and store the result in eax

partTwo:                          # Label on its own line
inc %eax                          # Increment the value in eax

movl $1, %eax                     # Indicate exit system call code (1)
movl $0, %ebx                     # Return value of the program (0)
int $0x80                         # Issue the kernel interrupt
.end                              # End assembling
```
## (64-bit) Program_3.2_GAS_Linux.s
```
.data                             # Section for variable definitions

decimalLiteral:    .byte 31       # Variable storing 31
hexLiteral:        .quad 0xF      # Variable storing F (15 in decimal)
charLiteral:       .byte 'A'      # Variable storing 65 in decimal

# Variable containing a string that has a line break and is null-terminated
stringLiteral:     .ascii "This string has\na line break in it.\0"

# Variable that calculates the value of an expression to determine the
# length, in bytes, of the variable "stringLiteral" by subtracting the
# starting memory address of the variable from the current memory address
.equ lenString, (. - stringLiteral)

.bss                              # Section for uninitialized variables
.lcomm unInitVariable, 8          # Uninitialized, 8-byte variable

.text                             # Section for instructions
.global _main                     # Make the label "_main"
                                  # available to the linker as an
                                  # entry point for the program
_main:                            # Label for program entry

# Label and instruction on
# the same line below
partOne: mov $10, %rax            # Assign 10 to the rax register
add hexLiteral(%rip), %rax        # Add the value in hexLiteral to
                                  # the contents of the rax register
                                  # and store the result in rax

partTwo:                          # Label on its own line
inc %rax                          # Increment the value in rax

mov $60, %rax                     # Set the system call for exit
xor %rdi, %rdi                    # Set the return value in rdi (0)
syscall                           # Issue the kernel interrupt
.end                              # End assembling
```

## NASM (32-bit) Program_3.2_NASM.asm
```
SECTION .data                     ; Section for variable definitions

decimalLiteral:   DB 31           ; Variable storing 31
hexLiteral:       DD 0Fh          ; Variable storing F (15 in decimal)
charLiteral:      DB 'A'          ; Variable storing 65 in decimal

; Variable containing a string that has a line break and is null-terminated
stringLiteral:    DB "This is a string that",0ah
                  DB "has a line break in it.",0

; Variable that calculates the value of an expression to determine the
; length, in bytes, of the variable "stringLiteral" by subtracting the
; starting memory address of the variable from the current memory address
lenString:        EQU ($ - stringLiteral)

SECTION .bss                      ; Section for uninitialized variables
unInitVariable:   RESD 1          ; 4-byte uninitialized variable

SECTION .text                     ; Section for instructions
global _main                      ; Make the label "_main"
                                  ; available to the linker as an
                                  ; entry point for the program
_main:                            ; Label for program entry

; Label and instruction on
; the same line below
partOne: mov eax, 10              ; Assign 10 to the eax register
add eax, hexLiteral               ; Add the value in hexLiteral to
                                  ; the contents of the eax register
                                  ; and store the result in eax

partTwo:                          ; Label on its own line
inc eax                           ; Increment the value in eax

mov eax, 1                        ; Indicate exit system call code (1)
mov ebx, 0                        ; Return value of the program (0)
int 80h                           ; Issue the kernel interrupt
```
## x86_64/Program_3.2_NASM.asm
```
SECTION .data                     ; Section for variable definitions

decimalLiteral:   DB 31           ; Variable storing 31
hexLiteral:       DQ 0Fh          ; Variable storing F (15 in decimal)
charLiteral:      DB 'A'          ; Variable storing 65 in decimal

; Variable containing a string that has a line break and is null-terminated
stringLiteral:    DB "This is a string that",0ah
                  DB "has a line break in it.",0

; Variable that calculates the value of an expression to determine the
; length, in bytes, of the variable "stringLiteral" by subtracting the
; starting memory address of the variable from the current memory address
lenString:        EQU ($ - stringLiteral)

SECTION .bss                      ; Section for uninitialized variables
unInitVariable:   RESQ 1          ; 4-byte uninitialized variable

SECTION .text                     ; Section for instructions
global _main                      ; Make the label "_main"
                                  ; available to the linker as an
                                  ; entry point for the program
_main:                            ; Label for program entry

; Label and instruction on
; the same line below
partOne: mov rax, 10              ; Assign 10 to the rax register
add rax, [hexLiteral]             ; Add the value in hexLiteral to
                                  ; the contents of the rax register
                                  ; and store the result in rax

partTwo:                          ; Label on its own line
inc rax                           ; Increment the value in rax

mov rax, 60                       ; Set the system call for exit
xor rdi, rdi                      ; Set the return value in rdi (0)
syscall                           ; Issue the kernel interrupt
```
