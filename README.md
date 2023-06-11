### Ex. No. 4
### Date: 28.4.23
# Implementation of half subtractor and full subtractor circuit using Verilog HDL
## Aim :
To design and implement half subtractor and full subtractor circuit and verify its truth table.
## Components Required:
1.	Laptop with Quartus software and modelsim software.
## Theory:
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

1) Half Subtractor
2) Full Subtractor
### 1.	Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference
and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
#### Truth table
 ![image](https://github.com/rvinifa/Subtractor/assets/133735746/5f2ca839-ef30-4b48-801c-029d4f1f80ed)

Sum = X’Y+XY’ = X ![image](https://github.com/rvinifa/Subtractor/assets/133735746/7822e41f-5b09-4d0d-90e9-996ac5f7b782)
 Y  
Carry=X’Y
#### Logic Diagram

![image](https://github.com/rvinifa/Subtractor/assets/133735746/ca83d3c0-9f56-4d5a-b02a-22224b853e03)
 
### 2.	Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 

#### Truth table
  .![image](https://github.com/rvinifa/Subtractor/assets/133735746/c6a11f80-9743-480e-a960-7a3174344b06)

![image](https://github.com/rvinifa/Subtractor/assets/133735746/ceb25c38-e81f-41e1-8b0f-20eb84207b2a)
 
#### Logic Diagram
 ![image](https://github.com/rvinifa/Subtractor/assets/133735746/ec7a895d-8893-4155-adc8-d15186f3f8b8)

## Procedure:
1.	Type the program in Quartus software.
2.	Compile and run the program.
3.	Generate the RTL schematic and save the logic diagram.
4.	Create nodes for inputs and outputs to generate the timing diagram.
5.	For different input combinations, generate the timing diagram.


## Program:
```
HALF SUBTRACTOR:
module exp4a(a,b,diff,borrow);
input a,b;
output diff,borrow;
wire adash;
xor(diff,a,b);
not(adash,a);
and(borrow,adash,b);
endmodule

FULL SUBTRACTOR:
module exp4b(a,b,c,diff,borrow);
input a,b,c;
output diff,borrow;
wire adash,x,p,q,r;
xor(x,b,c);
xor(diff,a,x);
not(adash,a);
and(p,adash,c);
and(q,b,c);
and(r,adash,b);
or(borrow,p,q,r);
endmodule
```
## RTL Schematic:
HALF SUBTRACTOR:
![DE4 1](https://github.com/VigneshkumaranNS/Subtractor/assets/119484483/afbf0cbe-9187-4d95-9f2c-26bafff64ba2)


FULL SUBTRACTOR:
![DE4 2](https://github.com/VigneshkumaranNS/Subtractor/assets/119484483/14e80d3e-bc9f-4bc5-93f5-bc57384e78de)


## Timing Diagram:
1.
![DE4 3](https://github.com/VigneshkumaranNS/Subtractor/assets/119484483/da1bca65-12a3-4536-9126-2177ba8edb3c)
2.
![DE4 4](https://github.com/VigneshkumaranNS/Subtractor/assets/119484483/725a14fb-f6ea-4b03-a99f-4e2c45866b77)
## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables are verified using Verilog HDL.
