# chapter 1

## summary
basic gate chips, up to 16-bit operations


## gates
Nand
Gate diagram

Truth table
a b | out
---------
0 0 | 1
0 1 | 1
1 0 | 1
1 1 | 0

Not
Truth table
in | out
--------
0  | 1
1  | 0

And
Truth table
a b | out
---------
0 0 | 0
0 1 | 0
1 0 | 0
1 1 | 1

Or
Truth table
a b | out
---------
0 0 | 0
0 1 | 1
1 0 | 1
1 1 | 1

Xor
Truth table
a b | out
---------
0 0 | 0
0 1 | 1
1 0 | 1
1 1 | 0

## project
Nand
- Builtin chip, no implementation required.

Not
- Look at Nand gate truth table where out is 0.
When a input pin is set to 1, out will change to inverse of b input pin.
Therefore I can make a Not gate from a Nand gate with the a pin set to 1
and the b pin is used as the in pin of the Not interface.

HDL
Nand(a=true, b=in, out=out);

And
- Made with Not gates

Or
Xor
Mux
DMux
Not16
And16
Or16
Xor16
Mux16
DMux16

