# chapter2

## summary
build chips up to an Arithmetic Logic Unit (ALU)

## binary representation
binary is represented in base 2 as opposed to normal decimal in base 10
[16]_10 = [1 0000]_2
word size is the number of bits used to represent a given data type

unsigned integers from of a given word size n has range [0, 2^n - 1]

two's complement is used for representing signed integers in binary
[-(2^(n-1), 2^(n-1) -1]

3 ways to turn positive two's complement negative
1. Keep first least significant 1 bit and all 0 bits LSB, flip all the other bits
2. Flip all bits then add 1
3. -x is 2^n - x where n is the word size of the integer

4 bit signed integer
3 2 1 0 | #
0 0 0 0   0
0 0 0 1   1
0 0 1 0   2
0 0 1 1   3
0 1 0 0   4
0 1 0 1   5
0 1 1 0   6
0 1 1 1   7
apply the methods listed above to get negative integers
1 1 1 1   -1
1 1 1 0   -2
1 1 0 1   -3
1 1 0 0   -4
1 0 1 1   -5
1 0 1 0   -6
1 0 0 1   -7
1 0 0 0   -8

# binary addition
half-adder
Truth table
a b | carry sum
0 0     0    0
0 1     0    1
1 0     0    1
1 1     1    0

Gate diagram

a-|\
  | |-sum
  | |
  | |-carry
b-|/ 

Input: a, b
Output: sum, carry
Function: sum = LSB of a + b
carry = MSB of a + b

- add 2 bits
- ignore carryover bit for most significant bit (MSB), the leftmost digit
- outputs sum and carry bit

full adder
Truth table
a b c | carry sum
0 0 0     0    0
0 0 1     0    1
0 1 0     0    1
0 1 1     1    0
1 0 0     0    1
1 0 1     1    0
1 1 0     1    0
1 1 1     1    1

Gate diagram
a-|\
  | |-sum
b-| |
  | |-carry
c-|/

- add 3 bits

16bit adder
- add 16 bits
a[16] b[16] | out[16]

ignore carryover bit for most significant bit (MSB), the leftmost digit
incrementer

ALU
2 inputs x[16] y[16]
6 control bits
1 out[16]
2 output bitsv zr ng

## project
half-adder
- half-adder truth table has outputs identical to 2 simple functions implemented in project1

Xor Truth table
a b | out
---------
0 0 | 0
0 1 | 1
1 0 | 1
1 1 | 0
- xor truth table output column matches the half-adder truth table's sum column

And truth table
a b | out
---------
0 0 | 0
0 1 | 0
1 0 | 0
1 1 | 1
- and truth table output column matches the half-adder truth table's carry column

HDL:

Xor(a=a, b=b, out=sum);
And(a=a, b=b, out=carry);

full-adder
- full-adder can be implemented from 2 half-adders and 1 additional gate, which is why they're called half and full. other implementations are possible even without half-adders


HDL:
adder
incrementer
ALU
