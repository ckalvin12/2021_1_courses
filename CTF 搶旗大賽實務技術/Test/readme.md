
# C==> Assembly
```
gcc -S -masm=intel bitwwise.c -o bitwise_intel.s -fno-asynchronous-unwind-tables
```
# ELF|binary  reverse to assembly
```

objdump -S -M intel objfile

objdump -S -j .text -M intel helloCTFer

objdump -S -j .text -M intel helloCTFer --no-show-raw-insn  

```
