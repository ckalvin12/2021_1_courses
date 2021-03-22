#
```
http://www.ece.ualberta.ca/~cmpe490/documents/axiom/GNU_Assembler
```
# Program 3.1 Sample Assembly Program - GAS, Clang/LLVM on Linux (32-bit)
```
組合語言的保留字不區分大小寫

識別字是由程式師所定義的名稱，用來表示變數、常數及過程等事物，
最多可以包含247 個字元
第一個字元不能是數位，且必須從英文字母（大寫的A 至z 及小寫的a 至z) 、底線（＿）、問號(?)、at 符號(@)及美元符號($)這五種中選擇
其後的字元則可以使用數字。


Assembler directives are instructions to the assembler to perform various bookkeeping tasks, storage reservation, and other control functions. 
```
```
首先定義一個32 位元的變數sum，然後將兩個數字相加25+50，最後把運算結果保存到該變數sum中。
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
