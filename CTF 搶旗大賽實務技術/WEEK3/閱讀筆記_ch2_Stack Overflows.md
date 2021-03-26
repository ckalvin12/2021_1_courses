#
```


```

## 1996 
```
Aleph One’s “Smashing the Stack for Fun and Profit.” 
Written in 1996 and published in Phrack magazine, 
the paper explained for the first time in a clear and concise manner how buffer
overflow vulnerabilities are possible and how they can be exploited. 

http://insecure.org/stf/smashstack.html.
https://inst.eecs.berkeley.edu/~cs161/fa08/papers/stack_smashing.pdf
```
## Buffers
```
A buffer ==>  a limited, contiguously allocated set of memory. 
             The most common buffer in C is an array.
             
             int array[5] = {1, 2, 3, 4, 5};        
```

```
#include <stdio.h>
#include <string.h>

int main ()
{
  int array[5] = {1, 2, 3, 4, 5};
  
  for(int i=0; i< 5; i++)
      {
        printf("array %d : address is %x and value is %d\n" ,i, &array[i] ,array[i]);
      }

    return 0;
}
```

```
gcc array.c -o array
root@kali:~# ./array 
array 0 : address is 5dc68440 and value is 1
array 1 : address is 5dc68444 and value is 2
array 2 : address is 5dc68448 and value is 3
array 3 : address is 5dc6844c and value is 4
array 4 : address is 5dc68450 and value is 5

```

# Stack overflows
```
no inherent bounds-checking exists on buffers in the C or C++ languages. 
the C language and its derivatives do not have a built-in function to 
ensure that data being copied into a buffer will not be larger than the buffer can hold.
```
### buffer Overflow 1
```
#include <stdio.h>
#include <string.h>

int main ()
{
  int array[5] = {1, 2, 3, 4, 5};

  printf("%d\n", array[5]);
  
  return 0;
}
```
```
root@kali:~# gcc bf1.c -o bf1
root@kali:~# ./bf1
32765
root@kali:~# ./bf1
32767
root@kali:~# ./bf1
32766
root@kali:~# ./bf1
32767
root@kali:~# ./bf1
32764
root@kali:~# ./bf1
32767
root@kali:~# ./bf1
32764
root@kali:~# ./bf1
32765
```
```
==> how easy it is to read past the end of a buffer; 
   C provides no built-in protection.
```

## 寫入的問題 bufferoverflow 2
```

```


