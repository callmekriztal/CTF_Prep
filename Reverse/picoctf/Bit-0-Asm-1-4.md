# Bit-O-Asm1 & Bit-O-Asm2

just find the value of eax (simple one line instruction) 
convert the hex to ascii

# Bit-O-Asm3

we are given a disassembly of a file 
we need to find the value of eax

## we can call rbp-0xc as a and rbp-0x8 as b

mov    DWORD PTR [rbp-0xc],0x9fe1a
#### a = 0x9fe1a
mov    DWORD PTR [rbp-0x8],0x4
#### b = 0x4
mov    eax,DWORD PTR [rbp-0xc] 
#### eax = a
imul   eax,DWORD PTR [rbp-0x8]
#### eax = eax * b
add    eax,0x1f5
#### eax = eax + 0x1f5
mov    DWORD PTR [rbp-0x4],eax
#### save result
mov    eax,DWORD PTR [rbp-0x4]
#### save result

now we can mathematically write this as 
result = (0x9fe1a * 4) + 0x1f5

find the hex and find it's equivalent ascii

# Bit-O-Asm4

<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a <br>
<+22>:    cmp    DWORD PTR [rbp-0x4],0x2710 <br>
<+29>:    jle    0x55555555514e <main+37> <br>
<+31>:    sub    DWORD PTR [rbp-0x4],0x65 <br>
<+35>:    jmp    0x555555555152 <main+41> <br>
<+37>:    add    DWORD PTR [rbp-0x4],0x65 <br>
<+41>:    mov    eax,DWORD PTR [rbp-0x4]


### let rbp-0x4 be a 
a = 0x9fe1a
if a <= 0x2710 jump to <main+37>
it evaluates to false 
next instruction <+35> is executed

a = a - 0x65
jump to <+41>
which is save result

C equivalent

if (a<=0x2710)
{
    a = a + 0x65
}
else
{
    a = a - 0x65
}

do the math and get the ascii value