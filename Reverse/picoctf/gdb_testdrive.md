# gdb testdrive


had nothing on execution
strings output didnt had a clue or flag

## part of question
$ chmod +x gdbme
$ gdb gdbme
(gdb) layout asm
(gdb) break *(main+99)
(gdb) run
(gdb) jump *(main+104)


while checking the asm via layout asm

+b 532a <main+99>    call   sleep@plt
   532f <main+104>   lea    -0x30(%rbp), %rax

so at main+99 the program is calling a sleep function which is why rest of the instructions are not executing

so the logic is that we will break at *(main+99) then run it which mean that the program execution will stop on reaching *(main+99) then we jump to *(main+104) effectively skipping the sleep call