[Cheat Sheet](https://cs.brown.edu/courses/cs033/docs/guides/x64_cheatsheet.pdf)

Only god knows what version of assembly I am trying to work with.
```nasm
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0xc],0x9fe1a
<+22>:    mov    DWORD PTR [rbp-0x8],0x4
<+29>:    mov    eax,DWORD PTR [rbp-0xc]
<+32>:    imul   eax,DWORD PTR [rbp-0x8]
<+36>:    add    eax,0x1f5
<+41>:    mov    DWORD PTR [rbp-0x4],eax
<+44>:    mov    eax,DWORD PTR [rbp-0x4]
<+47>:    pop    rbp
<+48>:    ret
```

[gdb](https://sourceware.org/gdb/):
debugger that can be used to debug assembly code. We can enter the debugger with the command 
```bash
gdb <file-name>
```

[call]():
The call instruction is an unconditional jump instruction. After it jumps, it will execute the code until it is done with the call (block?) and then return to the calling line. 
> This is like defining a function.

Registers:
rbp: The %rbp register is called the **base pointer** (and sometimes the frame pointer). For simple functions, an optimizing compiler generally treats this like any other callee-saved general-purpose register.

rsp: The %rsp register is used as the "**stack pointer**"; push and pop are used to add/remove values from the stack. The push instruction takes one operand: an immediate, a register, or a memory location.


