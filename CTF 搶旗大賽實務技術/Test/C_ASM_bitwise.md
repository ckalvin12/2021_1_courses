# itwwise.c 
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

# bitwise_intel.s
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
#
```
objdump -S -j .text -M intel bitwwise--no-show-raw-insn  
```
```
objdump -S -j .text -M intel bitwise --no-show-raw-insn  

bitwise:     file format elf32-i386


Disassembly of section .text:

08048310 <_start>:
 8048310:	xor    ebp,ebp
 8048312:	pop    esi
 8048313:	mov    ecx,esp
 8048315:	and    esp,0xfffffff0
 8048318:	push   eax
 8048319:	push   esp
 804831a:	push   edx
 804831b:	push   0x80484f0
 8048320:	push   0x8048490
 8048325:	push   ecx
 8048326:	push   esi
 8048327:	push   0x804840b
 804832c:	call   80482f0 <__libc_start_main@plt>
 8048331:	hlt    
 8048332:	xchg   ax,ax
 8048334:	xchg   ax,ax
 8048336:	xchg   ax,ax
 8048338:	xchg   ax,ax
 804833a:	xchg   ax,ax
 804833c:	xchg   ax,ax
 804833e:	xchg   ax,ax

08048340 <__x86.get_pc_thunk.bx>:
 8048340:	mov    ebx,DWORD PTR [esp]
 8048343:	ret    
 8048344:	xchg   ax,ax
 8048346:	xchg   ax,ax
 8048348:	xchg   ax,ax
 804834a:	xchg   ax,ax
 804834c:	xchg   ax,ax
 804834e:	xchg   ax,ax

08048350 <deregister_tm_clones>:
 8048350:	mov    eax,0x804a01f
 8048355:	sub    eax,0x804a01c
 804835a:	cmp    eax,0x6
 804835d:	jbe    8048379 <deregister_tm_clones+0x29>
 804835f:	mov    eax,0x0
 8048364:	test   eax,eax
 8048366:	je     8048379 <deregister_tm_clones+0x29>
 8048368:	push   ebp
 8048369:	mov    ebp,esp
 804836b:	sub    esp,0x14
 804836e:	push   0x804a01c
 8048373:	call   eax
 8048375:	add    esp,0x10
 8048378:	leave  
 8048379:	repz ret 
 804837b:	nop
 804837c:	lea    esi,[esi+eiz*1+0x0]

08048380 <register_tm_clones>:
 8048380:	mov    eax,0x804a01c
 8048385:	sub    eax,0x804a01c
 804838a:	sar    eax,0x2
 804838d:	mov    edx,eax
 804838f:	shr    edx,0x1f
 8048392:	add    eax,edx
 8048394:	sar    eax,1
 8048396:	je     80483b3 <register_tm_clones+0x33>
 8048398:	mov    edx,0x0
 804839d:	test   edx,edx
 804839f:	je     80483b3 <register_tm_clones+0x33>
 80483a1:	push   ebp
 80483a2:	mov    ebp,esp
 80483a4:	sub    esp,0x10
 80483a7:	push   eax
 80483a8:	push   0x804a01c
 80483ad:	call   edx
 80483af:	add    esp,0x10
 80483b2:	leave  
 80483b3:	repz ret 
 80483b5:	lea    esi,[esi+eiz*1+0x0]
 80483b9:	lea    edi,[edi+eiz*1+0x0]

080483c0 <__do_global_dtors_aux>:
 80483c0:	cmp    BYTE PTR ds:0x804a01c,0x0
 80483c7:	jne    80483dc <__do_global_dtors_aux+0x1c>
 80483c9:	push   ebp
 80483ca:	mov    ebp,esp
 80483cc:	sub    esp,0x8
 80483cf:	call   8048350 <deregister_tm_clones>
 80483d4:	mov    BYTE PTR ds:0x804a01c,0x1
 80483db:	leave  
 80483dc:	repz ret 
 80483de:	xchg   ax,ax

080483e0 <frame_dummy>:
 80483e0:	mov    eax,0x8049f10
 80483e5:	mov    edx,DWORD PTR [eax]
 80483e7:	test   edx,edx
 80483e9:	jne    80483f0 <frame_dummy+0x10>
 80483eb:	jmp    8048380 <register_tm_clones>
 80483ed:	lea    esi,[esi+0x0]
 80483f0:	mov    edx,0x0
 80483f5:	test   edx,edx
 80483f7:	je     80483eb <frame_dummy+0xb>
 80483f9:	push   ebp
 80483fa:	mov    ebp,esp
 80483fc:	sub    esp,0x14
 80483ff:	push   eax
 8048400:	call   edx
 8048402:	add    esp,0x10
 8048405:	leave  
 8048406:	jmp    8048380 <register_tm_clones>

0804840b <main>:
 804840b:	lea    ecx,[esp+0x4]
 804840f:	and    esp,0xfffffff0
 8048412:	push   DWORD PTR [ecx-0x4]
 8048415:	push   ebp
 8048416:	mov    ebp,esp
 8048418:	push   ecx
 8048419:	sub    esp,0x14
 804841c:	mov    DWORD PTR [ebp-0x10],0x69
 8048423:	mov    DWORD PTR [ebp-0xc],0x1a
 804842a:	mov    eax,DWORD PTR [ebp-0x10]
 804842d:	and    eax,DWORD PTR [ebp-0xc]
 8048430:	push   eax
 8048431:	push   DWORD PTR [ebp-0xc]
 8048434:	push   DWORD PTR [ebp-0x10]
 8048437:	push   0x8048510
 804843c:	call   80482e0 <printf@plt>
 8048441:	add    esp,0x10
 8048444:	mov    eax,DWORD PTR [ebp-0x10]
 8048447:	or     eax,DWORD PTR [ebp-0xc]
 804844a:	push   eax
 804844b:	push   DWORD PTR [ebp-0xc]
 804844e:	push   DWORD PTR [ebp-0x10]
 8048451:	push   0x804851e
 8048456:	call   80482e0 <printf@plt>
 804845b:	add    esp,0x10
 804845e:	mov    eax,DWORD PTR [ebp-0x10]
 8048461:	xor    eax,DWORD PTR [ebp-0xc]
 8048464:	push   eax
 8048465:	push   DWORD PTR [ebp-0xc]
 8048468:	push   DWORD PTR [ebp-0x10]
 804846b:	push   0x804852b
 8048470:	call   80482e0 <printf@plt>
 8048475:	add    esp,0x10
 8048478:	mov    eax,0x0
 804847d:	mov    ecx,DWORD PTR [ebp-0x4]
 8048480:	leave  
 8048481:	lea    esp,[ecx-0x4]
 8048484:	ret    
 8048485:	xchg   ax,ax
 8048487:	xchg   ax,ax
 8048489:	xchg   ax,ax
 804848b:	xchg   ax,ax
 804848d:	xchg   ax,ax
 804848f:	nop

08048490 <__libc_csu_init>:
 8048490:	push   ebp
 8048491:	push   edi
 8048492:	push   esi
 8048493:	push   ebx
 8048494:	call   8048340 <__x86.get_pc_thunk.bx>
 8048499:	add    ebx,0x1b67
 804849f:	sub    esp,0xc
 80484a2:	mov    ebp,DWORD PTR [esp+0x20]
 80484a6:	lea    esi,[ebx-0xf4]
 80484ac:	call   80482ac <_init>
 80484b1:	lea    eax,[ebx-0xf8]
 80484b7:	sub    esi,eax
 80484b9:	sar    esi,0x2
 80484bc:	test   esi,esi
 80484be:	je     80484e5 <__libc_csu_init+0x55>
 80484c0:	xor    edi,edi
 80484c2:	lea    esi,[esi+0x0]
 80484c8:	sub    esp,0x4
 80484cb:	push   DWORD PTR [esp+0x2c]
 80484cf:	push   DWORD PTR [esp+0x2c]
 80484d3:	push   ebp
 80484d4:	call   DWORD PTR [ebx+edi*4-0xf8]
 80484db:	add    edi,0x1
 80484de:	add    esp,0x10
 80484e1:	cmp    edi,esi
 80484e3:	jne    80484c8 <__libc_csu_init+0x38>
 80484e5:	add    esp,0xc
 80484e8:	pop    ebx
 80484e9:	pop    esi
 80484ea:	pop    edi
 80484eb:	pop    ebp
 80484ec:	ret    
 80484ed:	lea    esi,[esi+0x0]

080484f0 <__libc_csu_fini>:
 80484f0:	repz ret 
```
