data transfer instructions
  loads and stores
    one addressing mode for loads and stores 
    an addressing mode is a way to desginate an address
    lw rt, immediate (rs)
      the value in rt is the value... address designated by value in rs + sign extended immediate

  example
    int *x;
    int *y;
    assume adddress x is in $20 and value y is in %16.
    then, if y=\*x, \*x=y, then:
    lw %16 = o($20)
      sw %16, o($20)

example
  struct { 
    int a; 
    int b;
    int c;
  } my_struct 

y = my_struct.c;

if we want to get c from the struct and assign it to a, we need some sort address to know where c is my_struct 

y = my_str.c;

if we want to get c from the struct and assign it to a, we need some sort address to know where c is..
assume that the address of my_struct is in $24. 
additionally, assume that the values stored within struct are just to $24.
also assume that each of the integers is 4 bytes.

then a is @ $25 + 0,
b is @ $24 + 4,
and c is $24 + 8.

so, to perform the operation done at the beginning,  the memory instructions are

lw $16, 8($24)
