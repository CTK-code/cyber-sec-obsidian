rgdb, or gnu project debugger, lets us see whats going on in a program as it runs or at point of failure.
Its a debugger, ya kno?
```bash
gdb program_to_debug
```
###### `(gdb) disassemble main`
Displays the program's assembly code.
```assembly
(gdb) disassemble main
Dump of assembler code for function main:
   0x0000000000001129 <+0>:	endbr64
   0x000000000000112d <+4>:	push   %rbp
   0x000000000000112e <+5>:	mov    %rsp,%rbp
   0x0000000000001131 <+8>:	mov    %edi,-0x4(%rbp)
   0x0000000000001134 <+11>:	mov    %rsi,-0x10(%rbp)
   0x0000000000001138 <+15>:	mov    $0x86342,%eax
   0x000000000000113d <+20>:	pop    %rbp
   0x000000000000113e <+21>:	ret
End of assembler dump.
```

##### `(gdb) run`
Runs the program until our breakpoint.
###### `(gdb) break *main+59` 
Sets a breakpoint at the instruction at +59.

###### `(gdb) info registers eax`
Prints out the value at eax in hexadecimal and decimal

###### `(gdb) `x/4xb addr`
This prints out the value at the designated address
