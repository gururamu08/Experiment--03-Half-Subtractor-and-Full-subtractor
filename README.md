# Experiment--03-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure



Write the detailed procedure here 


## Program:
/*
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: GURUMOORTHI R
RegisterNumber:  212222230042
*/
```
### half sub:
module halfsubtractor(A,B,Diff,Borrow);
input A,B;
output Diff,Borrow;
wire x;
xor (Diff, A,B);
not(x,A);
and(Borrow,x,B);
endmodule

### full sub:

module fullsubtractor(A,B,C,Diff,Borrow);
input A,B,C;
output Diff,Borrow;
wire p;
assign Diff = ((A^B)^C);
not(p,A);
assign Borrow = ((p&B)|(p&C)|(B&C));
endmodule
```

## Output:

## Truthtable
## HALF:

![image](https://user-images.githubusercontent.com/118707009/233260867-7915e498-4466-418f-84db-dd580522c402.png)

## FULL:

![image](https://user-images.githubusercontent.com/118707009/233261028-bd9d9ce7-cafb-4857-806c-b205fabf195b.png)


##  RTL realization

## HALF

![image](https://user-images.githubusercontent.com/118707009/233261105-6e73b168-9967-4d31-9eca-03582bf931e4.png)

## FULL

![image](https://user-images.githubusercontent.com/118707009/233276077-95b4cbda-99fe-4da1-8195-03180d86d58a.png)

## TIMING DIAGRAM

## HALF

![image](https://user-images.githubusercontent.com/118707009/233261553-42640545-f9bf-4883-a3a9-858716f46836.png)

## FULL


![DE](https://user-images.githubusercontent.com/118707009/233262661-ddbe4786-bb75-4f4e-855f-4be74411e03e.png)



## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
