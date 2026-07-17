# chapter2

## summary
build chips up to an Arithmetic Logic Unit (ALU)

## binary representation
binary is represented in base 2 as opposed to normal decimal in base 10
[16]_10 = [1 0000]_2
word size is the number of bits used to represent a given data type

unsigned integers from of a given word size n do 0 to 2^n - 1

two's complement is used for representing signed integers in binary
-(2^(n-1) to 2^(n-1) -1

Methods to go from a positive two's complement to negative
1. Keep first least significant 1 bit and all 0 bits LSB, flip all the other bits
2. Flip all bits then add 1
3. -x is 2^n - x where n is the word size of the integer


# binary addition
half-adder
- add 2 bits
- ignore carryover bit for most significant bit (MSB), the leftmost digit
- outputs sum and carry bit
full adder
- add 3 bits

16bit adder
- add 16 bits

ignore carryover bit for most significant bit (MSB), the leftmost digit
incrementer

ALU
2 inputs x[16] y[16]
6 control bits
1 out[16]
2 output bitsv zr ng

## project
half-adder
a b | carry sum
0 0     0    0
0 1     0    1
1 0     0    1
1 1     1    0

full-adder
a b c | carry sum
0 0 0
0 0 1
0 1 0
0 1 1
1 0 0
1 0 1
1 1 0
1 1 1

adder
a[16] b[16] | out[16]


incrementer
in | out
in  in+1

ALU
