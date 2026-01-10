# gdb baby step 1

we were required to find the value of eax 
since the program was small i was able find it just by reading the asm

# gdb baby step 2

similar but the eax register has the value of rbx

so just looking up won't guarrenties the success 
check the functions
info functions

now dissassemble main

the logic is that we break the program at the instruction immediatly to the eax instructions :- means say at line 20 there is eax be break at 21 ,run it 
then check the content of eax register 
break *address

run 

info register eax

# gdb baby step 3

a constant is loaded into a register we have to lookup the register and find that value 

so put a break at the instruction after the that register instruction
and run it

examine the register  
syntax of examine :- x / <count> <format> <size> <address>

x/4xb is a memory examine command in GDB. It tells GDB to:
x → examine memory
/4 → show 4 units
x → display each unit in hexadecimal
b → and interpret each unit as a byte

why 4 units ?
it's mentioned in question 

x/4xb $rbp-0x4

hence the flag contents are obtained

# gdb baby step 4

here inside main a function is called which multiplies a constant with eax
we need to find the constant 

break before the function call since the instruction above it uses eax and 
then break it after the multiplication operation:- instruction after the last usage of eax

run and find the content of register eax
now we get x which is the content of eax 

continue to the next breakpoint 
info register eax
now we get y which is the content of eax 

now if we take x/y we get the constant that was mulitipied with eax 

hence the flag contents are obtained