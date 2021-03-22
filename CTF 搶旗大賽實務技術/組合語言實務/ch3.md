#
```
http://www.ece.ualberta.ca/~cmpe490/documents/axiom/GNU_Assembler
```
# Program 3.1 Sample Assembly Program - GAS, Clang/LLVM on Linux (32-bit)
```
首先定義一個32 位元的變數，然後將兩個數位相加，最後把運算結果保存到該變蜇中。
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
