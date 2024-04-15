```
section .data
        result dw 1
        num dw 4


section .text
        global _start

_start:

        mov eax, 4
        call factorial


        mov eax,1
        xor ebx, ebx
        int 0x80

factorial:
        cmp eax, 1
        jle .base case
        dec eax
        push eax
        call factorial
        pop bx
        mul bx
        ret

.base_case
      mov eax, [result]
      ret
```
