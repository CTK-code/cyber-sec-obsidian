gdb, or gnu project debugger, lets us see whats going on in a program as it runs or at point of failure.
Its a debugger, ya kno?
```bash
gdb program_to_debug
```
`(gdb) disassemble main` Displays the program's assembly code.
`(gdb) break *main+59`  Sets a breakpoint at the instruction at +59.