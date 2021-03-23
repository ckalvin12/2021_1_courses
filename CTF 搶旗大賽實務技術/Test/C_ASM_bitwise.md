#
```
#include <stdio.h>

int main(void)
{
   int a=105,b=26;
   printf("%d and %d=%d\n",a,b,a&b);    
   printf("%d or %d=%d\n",a,b,a|b);
   printf("%d XOR %d=%d\n",a,b,a^b);
   return 0;
}
```

#
```
gcc -S -masm=intel bitwwise.c -o bitwise_intel.s -fno-asynchronous-unwind-tables
```
```
cat bitwise_intel.s 
	.file	"bitwise.c"
	.intel_syntax noprefix
	.section	.rodata
.LC0:
	.string	"%d and %d=%d\n"
.LC1:
	.string	"%d or %d=%d\n"
.LC2:
	.string	"%d XOR %d=%d\n"
	.text
	.globl	main
	.type	main, @function
main:
	lea	ecx, [esp+4]
	and	esp, -16
	push	DWORD PTR [ecx-4]
	push	ebp
	mov	ebp, esp
	push	ecx
	sub	esp, 20
	mov	DWORD PTR [ebp-16], 105
	mov	DWORD PTR [ebp-12], 26
	mov	eax, DWORD PTR [ebp-16]
	and	eax, DWORD PTR [ebp-12]
	push	eax
	push	DWORD PTR [ebp-12]
	push	DWORD PTR [ebp-16]
	push	OFFSET FLAT:.LC0
	call	printf
	add	esp, 16
	mov	eax, DWORD PTR [ebp-16]
	or	eax, DWORD PTR [ebp-12]
	push	eax
	push	DWORD PTR [ebp-12]
	push	DWORD PTR [ebp-16]
	push	OFFSET FLAT:.LC1
	call	printf
	add	esp, 16
	mov	eax, DWORD PTR [ebp-16]
	xor	eax, DWORD PTR [ebp-12]
	push	eax
	push	DWORD PTR [ebp-12]
	push	DWORD PTR [ebp-16]
	push	OFFSET FLAT:.LC2
	call	printf
	add	esp, 16
	mov	eax, 0
	mov	ecx, DWORD PTR [ebp-4]
	leave
	lea	esp, [ecx-4]
	ret
	.size	main, .-main
	.ident	"GCC: (Ubuntu 5.4.0-6ubuntu1~16.04.12) 5.4.0 20160609"
	.section	.note.GNU-stack,"",@progbits

```
