#
```
https://github.com/bytes4breakfast/shellcoders-handbook/blob/master/noprotec.sh
```
```
#!/bin/bash

usage()
{
 echo "Compile without memory protections. Usage:"
 echo "noprotec <source> <dest. name>"
 echo "Example:"
 echo "   no_protec mycode.c myprogram.o"
}

if [ -z "$1" ]; then

 echo "No source file specified"
 usage
 exit 1

elif [ -z "$2" ]; then
 
 in=$1
 out=$(echo "$1" | cut -d'.' -f1) # Remove .c extension for output if no output name is specified.
 gcc -m32 -zno_stack_protector -z execstack -no-pie -o $out $in -ggdb

else 
 in=$1
 out=$2
 gcc -m32 -zno_stack_protector -z execstack -no-pie -o $out $in -ggdb

fi
```
