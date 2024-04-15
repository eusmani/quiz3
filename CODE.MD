```
section .text
        global _start

_start:
        mov eax,2       ;array length (0-2)
        mov ebx,0       ;initializing  ebx 0
        mov ecx,array   ;move array's address from the memory to the register
        								;the array address is equal to the address of 
        								;the first element

top:
        add ebx,[ecx]   ;add content of the array's first element with the ebx
        add ecx,4       ;fetch the next element in the array which is 4 bytes away
        dec eax         ;eax will work as a counter which is equal to the 
                        ;array length
        jnz top         ;jump not zero to the label top

        mov eax,1       
        int 0x80

section .data
        array dd 5,10,15        ;size double data 4 bytes
```
