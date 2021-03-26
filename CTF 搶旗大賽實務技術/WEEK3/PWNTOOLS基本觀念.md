# registers 暫存器
```
registers can be grouped into four categories:
[1]General purpose==>mathematical operations
       EAX, EBX, and ECX 
       ==>can be used to store data and addresses, 
          offset addresses, perform counting functions, and many other things.
          
       重要阿 ~~~the extended stack pointer register(ESP) 
                  simply the stack pointer. 
       ESP points to the memory address where the next stack operation 
       will take place. 
       In order to understand stack overflows in

[2]Segment ==>
      the segment registers are 16 bit (other registers are 32 bits in size). 
      Segment registers ==>  CS, DS, and SS, 
          ==>  are used to keep track of segments and 
                to allow backward compatibility with 16-bit applications.
                
[3]Control ==> control the function of the processor
           ==> Extended Instruction Pointer (EIP)
                            or simply the Instruction Pointer. 
           ==>  EIP contains the address of the next machine instruction 
                 to be executed. 
                 Naturally, if you want to control the execution path of a program, 
                 it is important to have the ability to access and change 
                 the value stored in the EIP register.


```

```
