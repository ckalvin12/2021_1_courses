# peda的使用
```
https://www.jianshu.com/p/283b5466684b

    peda一款實用的GDB外掛程式
    增強gdb的顯示：在調試過程中著色並顯示反彙編代碼，寄存器和記憶體資訊。
    添加命令以支持調試和利用開發（有關命令使用的完整列表peda help）
```
# 安裝
```
相較於pwndbg，這個安裝相當快捷
pip install peda
```
```
git clone https://github.com/longld/peda.git ~/peda
echo "source ~/peda/peda.py" >> ~/.gdbinit 
```
# 基礎命令
```
file 路徑　-　附加檔
break *0x400100 (b main) - 在 0x400100 處下中斷點
tb  - 一次性中斷點
info b - 查看中斷點信息
enable   -   啟動中斷點
disable  -   禁用中斷點
delete [number]  -  刪除中斷點
watch *(int *)0x08044530  -  在記憶體0x0804453處的資料改變時stop
p $eax - 輸出eax的內容
set $eax=4 - 修改變數值
```
```
c - 繼續運行
r - 開始運行
ni - 單步步過
si - 單步步入
fini - 運行至函數剛結束處
return expression - 將函數返回值指定為expression
bt - 查看當前棧幀
info f - 查看當前棧幀
context - 查看運行上下文
stack - 查看當前堆疊
call func - 強制函式呼叫
stack 100 - 外掛程式提供的，顯示棧中100項
find xxx　 - 快速查找，很實用
```
```
x/<n/f/u> <addr>     n、f、u是可選的參數。
x /4xg $ebp：查看ebp開始的4個8位元組內容
x/wx $esp 　　以4位元組16進制顯示棧中內容


b表示單字節，h表示雙位元組，w表示四字 節，g表示八位元組
s 按字串輸出
x 按十六進位格式顯示變數。
d 按十進位格式顯示變數。
u 按十六進位格式顯示無符號整型。
o 按八進制格式顯示變數。
t 按二進位格式顯示變數。
a 按十六進位格式顯示變數。
c 按字元格式顯示變數。
f 按浮點數格式顯示變數。
i：反彙編
```
```
但是實際的組合就那麼幾種：
x/s 位址　　查看字串
x/wx 地址　　查看DWORD
x/c 地址　　單字節查看
x/16x $esp+12 查看寄存器偏移
```
```
set args  - 可指定運行時參數。（如：set args 10 20 30 40 50）
show args  - 命令可以查看設置好的運行參數。
```

# 簡單練習
```
下酨 PWN-CTF  ==> level 1:pass

gdb
```
```

載入檔案
gdb-peda$ file pass
Reading symbols from pass...(no debugging symbols found)...done.

先反組譯main()函數

gdb-peda$ disas main
Dump of assembler code for function main:
   0x000000000040080e <+0>:	push   rbp
   0x000000000040080f <+1>:	mov    rbp,rsp
   0x0000000000400812 <+4>:	sub    rsp,0x20
   0x0000000000400816 <+8>:	mov    rax,QWORD PTR [rip+0x200843]        # 0x601060 <stdout@@GLIBC_2.2.5>
   0x000000000040081d <+15>:	mov    ecx,0x0
   0x0000000000400822 <+20>:	mov    edx,0x2
   0x0000000000400827 <+25>:	mov    esi,0x0
   0x000000000040082c <+30>:	mov    rdi,rax
   0x000000000040082f <+33>:	call   0x4005b0 <setvbuf@plt>
   0x0000000000400834 <+38>:	mov    rax,QWORD PTR [rip+0x200835]        # 0x601070 <stdin@@GLIBC_2.2.5>
   0x000000000040083b <+45>:	mov    ecx,0x0
   0x0000000000400840 <+50>:	mov    edx,0x2
   0x0000000000400845 <+55>:	mov    esi,0x0
   0x000000000040084a <+60>:	mov    rdi,rax
   0x000000000040084d <+63>:	call   0x4005b0 <setvbuf@plt>
   0x0000000000400852 <+68>:	mov    DWORD PTR [rbp-0x4],0x4d2
   0x0000000000400859 <+75>:	mov    edi,0x400978
   0x000000000040085e <+80>:	call   0x400560 <puts@plt>
   0x0000000000400863 <+85>:	mov    edi,0x4009a0
   0x0000000000400868 <+90>:	call   0x400560 <puts@plt>
   0x000000000040086d <+95>:	mov    edi,0x4009ca
   0x0000000000400872 <+100>:	mov    eax,0x0
   0x0000000000400877 <+105>:	call   0x400580 <printf@plt>
   0x000000000040087c <+110>:	lea    rax,[rbp-0x20]
   0x0000000000400880 <+114>:	mov    edx,0x28
   0x0000000000400885 <+119>:	mov    rsi,rax
   0x0000000000400888 <+122>:	mov    edi,0x0
   0x000000000040088d <+127>:	mov    eax,0x0
   0x0000000000400892 <+132>:	call   0x400590 <read@plt>
   0x0000000000400897 <+137>:	cmp    DWORD PTR [rbp-0x4],0xdeadbeef
   0x000000000040089e <+144>:	jne    0x4008c0 <main+178>
   0x00000000004008a0 <+146>:	mov    edi,0x4009e6
   0x00000000004008a5 <+151>:	call   0x400560 <puts@plt>
   0x00000000004008aa <+156>:	mov    eax,0x0
   0x00000000004008af <+161>:	call   0x4006c6 <printTheKey>
   0x00000000004008b4 <+166>:	mov    edi,0x4009f5
   0x00000000004008b9 <+171>:	call   0x400570 <system@plt>
   0x00000000004008be <+176>:	jmp    0x4008ca <main+188>
   0x00000000004008c0 <+178>:	mov    edi,0x400a08
   0x00000000004008c5 <+183>:	call   0x400560 <puts@plt>
   0x00000000004008ca <+188>:	mov    eax,0x0
   0x00000000004008cf <+193>:	leave  
   0x00000000004008d0 <+194>:	ret    
End of assembler dump.
  
看看上面==>找 call ...
       ==>設定斷點
gdb-peda$ b *0x000000000040084d
Breakpoint 1 at 0x40084d


執行 run 

gdb-peda$ r
Starting program: /root/Downloads/pass 

[----------------------------------registers-----------------------------------]
RAX: 0x7ffff7faaa00 --> 0xfbad2088 
RBX: 0x0 
RCX: 0x0 
RDX: 0x2 
RSI: 0x0 
RDI: 0x7ffff7faaa00 --> 0xfbad2088 
RBP: 0x7fffffffe1a0 --> 0x4008e0 (<__libc_csu_init>:	push   r15)
RSP: 0x7fffffffe180 --> 0x4008e0 (<__libc_csu_init>:	push   r15)
RIP: 0x40084d (<main+63>:	call   0x4005b0 <setvbuf@plt>)
R8 : 0x7ffff7fac8c0 --> 0x0 
R9 : 0x7ffff7fb1500 (0x00007ffff7fb1500)
R10: 0xfffffffffffff41c 
R11: 0x7ffff7e61200 (<__GI__IO_setvbuf>:	push   r13)
R12: 0x4005d0 (<_start>:	xor    ebp,ebp)
R13: 0x7fffffffe280 --> 0x1 
R14: 0x0 
R15: 0x0
EFLAGS: 0x202 (carry parity adjust zero sign trap INTERRUPT direction overflow)
[-------------------------------------code-------------------------------------]
   0x400840 <main+50>:	mov    edx,0x2
   0x400845 <main+55>:	mov    esi,0x0
   0x40084a <main+60>:	mov    rdi,rax
=> 0x40084d <main+63>:	call   0x4005b0 <setvbuf@plt>
   0x400852 <main+68>:	mov    DWORD PTR [rbp-0x4],0x4d2
   0x400859 <main+75>:	mov    edi,0x400978
   0x40085e <main+80>:	call   0x400560 <puts@plt>
   0x400863 <main+85>:	mov    edi,0x4009a0
Guessed arguments:
arg[0]: 0x7ffff7faaa00 --> 0xfbad2088 
arg[1]: 0x0 
arg[2]: 0x2 
arg[3]: 0x0 
[------------------------------------stack-------------------------------------]
0000| 0x7fffffffe180 --> 0x4008e0 (<__libc_csu_init>:	push   r15)
0008| 0x7fffffffe188 --> 0x4005d0 (<_start>:	xor    ebp,ebp)
0016| 0x7fffffffe190 --> 0x7fffffffe280 --> 0x1 
0024| 0x7fffffffe198 --> 0x0 
0032| 0x7fffffffe1a0 --> 0x4008e0 (<__libc_csu_init>:	push   r15)
0040| 0x7fffffffe1a8 --> 0x7ffff7e1309b (<__libc_start_main+235>:	mov    edi,eax)
0048| 0x7fffffffe1b0 --> 0x0 
0056| 0x7fffffffe1b8 --> 0x7fffffffe288 --> 0x7fffffffe56b ("/root/Downloads/pass")
[------------------------------------------------------------------------------]
Legend: code, data, rodata, value

Breakpoint 1, 0x000000000040084d in main ()

當停在中斷點後 檢查一下你想看的資料 registers

gdb-peda$ info reg
rax            0x7ffff7faaa00      0x7ffff7faaa00
rbx            0x0                 0x0
rcx            0x0                 0x0
rdx            0x2                 0x2
rsi            0x0                 0x0
rdi            0x7ffff7faaa00      0x7ffff7faaa00
rbp            0x7fffffffe1a0      0x7fffffffe1a0
rsp            0x7fffffffe180      0x7fffffffe180
r8             0x7ffff7fac8c0      0x7ffff7fac8c0
r9             0x7ffff7fb1500      0x7ffff7fb1500
r10            0xfffffffffffff41c  0xfffffffffffff41c
r11            0x7ffff7e61200      0x7ffff7e61200
r12            0x4005d0            0x4005d0
r13            0x7fffffffe280      0x7fffffffe280
r14            0x0                 0x0
r15            0x0                 0x0
rip            0x40084d            0x40084d <main+63>
eflags         0x202               [ IF ]
cs             0x33                0x33
ss             0x2b                0x2b
ds             0x0                 0x0
es             0x0                 0x0
fs             0x0                 0x0
gs             0x0                 0x0

使用vmmap 查看⽬前程式的記憶體分佈，以及 rwx 權限設定

gdb-peda$ vmmap
Start              End                Perm	Name
0x00400000         0x00401000         r-xp	/root/Downloads/pass
0x00600000         0x00601000         r--p	/root/Downloads/pass
0x00601000         0x00602000         rw-p	/root/Downloads/pass
0x00007ffff7def000 0x00007ffff7e11000 r--p	/usr/lib/x86_64-linux-gnu/libc-2.28.so
0x00007ffff7e11000 0x00007ffff7f59000 r-xp	/usr/lib/x86_64-linux-gnu/libc-2.28.so
0x00007ffff7f59000 0x00007ffff7fa5000 r--p	/usr/lib/x86_64-linux-gnu/libc-2.28.so
0x00007ffff7fa5000 0x00007ffff7fa6000 ---p	/usr/lib/x86_64-linux-gnu/libc-2.28.so
0x00007ffff7fa6000 0x00007ffff7faa000 r--p	/usr/lib/x86_64-linux-gnu/libc-2.28.so
0x00007ffff7faa000 0x00007ffff7fac000 rw-p	/usr/lib/x86_64-linux-gnu/libc-2.28.so
0x00007ffff7fac000 0x00007ffff7fb2000 rw-p	mapped
0x00007ffff7fd0000 0x00007ffff7fd3000 r--p	[vvar]
0x00007ffff7fd3000 0x00007ffff7fd5000 r-xp	[vdso]
0x00007ffff7fd5000 0x00007ffff7fd6000 r--p	/usr/lib/x86_64-linux-gnu/ld-2.28.so
0x00007ffff7fd6000 0x00007ffff7ff4000 r-xp	/usr/lib/x86_64-linux-gnu/ld-2.28.so
0x00007ffff7ff4000 0x00007ffff7ffc000 r--p	/usr/lib/x86_64-linux-gnu/ld-2.28.so
0x00007ffff7ffc000 0x00007ffff7ffd000 r--p	/usr/lib/x86_64-linux-gnu/ld-2.28.so
0x00007ffff7ffd000 0x00007ffff7ffe000 rw-p	/usr/lib/x86_64-linux-gnu/ld-2.28.so
0x00007ffff7ffe000 0x00007ffff7fff000 rw-p	mapped
0x00007ffffffde000 0x00007ffffffff000 rw-p	[stack]
```
