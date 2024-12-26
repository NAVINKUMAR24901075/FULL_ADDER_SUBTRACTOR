# NAME : S.NAVINKUMAR
# REG.NO : 24901075
# EXPERIMENT-4 : FULL ADDER AND SUBTRACTOR


# AIM:
 
To design a Full Adder and Full Subtractor circuit and verify its truth table in Quartus using Verilog programming.

# EQUIPMENTS REQURIED:

Hardware – PCs, Cyclone II , USB flasher

Software – Quartus prime

# FULL ADDER AND FULL SUBTRACTOR

# FULL ADDER:

Full adder is a digital circuit used to calculate the sum of three binary bits. It consists of three inputs and two outputs. Two of the input variables, denoted by A and B, represent the two significant bits to be added. The third input, Cin, represents the carry from the previous lower significant position. Two outputs are necessary because the arithmetic sum of three binary digits ranges in value from 0 to 3, and binary 2 or 3 needs two digits. The two outputs are sum and carry.

Sum =A’B’Cin + A’BCin’ + ABCin + AB’Cin’ = A ⊕ B ⊕ Cin 

Carry = AB + ACin + BCin

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/0f30ba51-5ffb-4198-845f-18e054f675e7)

**Figure -1 FULL ADDER**

# FULL SUBTRACTOR:

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/02b24f51-ab51-4304-9ad6-7b81ffc1ead5)

Diff = A ⊕ B ⊕ Bin 

Borrow out = A'Bin + A'B + BBin

# PROCEDURE:

1.Type the program in Quartus software.

2.Compile and run the program.

3.Generate the RTL schematic and save the logic diagram.

4.Create nodes for inputs and outputs to generate the timing diagram.

5.For different input combinations generate the timing diagram.

# Full Adder
Inputs: Three inputs: A, B (the two bits to be added), and Cin (the carry-in bit from a previous addition).
Outputs: Two outputs: Sum (the resulting sum) and Cout (the carry-out bit).
Logic:
Sum = A ^ B ^ Cin (XOR operation).
Cout = (A & B) | (A & Cin) | (B & Cin) (carry occurs if at least two inputs are 1).

# Full Subtractor
Inputs: Three inputs: A, B (the two bits, where A - B is calculated), and Bin (the borrow-in from a previous subtraction).
Outputs: Two outputs: Diff (the resulting difference) and Bout (the borrow-out bit).
Logic:
Diff = A ^ B ^ Bin (XOR operation).
Bout = (~A & B) | ((~A | B) & Bin) (borrow occurs if A is less than B or needs a borrow).
Both circuits follow simple XOR logic for the primary result and AND-OR logic to determine carry or borrow conditions.

# PROGRAM:
~~~~~
module fulladdsub(a,b,cin,bin,sum,carry,difference,borrow);
input a,b,cin,bin;
output sum,carry,difference,borrow;
assign sum=a^b^cin;
assign carry=(a^b)&cin|a&b;
assign difference=a^b^bin;
assign borrow=~(a^b)&bin|(~a)&b;
endmodule
~~~~~
# TRUTH TABLE:

![Screenshot 2024-11-14 051254](https://github.com/user-attachments/assets/1a3433d0-66ea-4eb8-a1cf-26d75dfd6c50)

![Screenshot 2024-11-14 051519](https://github.com/user-attachments/assets/1c09fec5-9b75-4741-a8ef-32b347e62909)

# RTL OUTPUT:

![Screenshot 2024-11-14 050503](https://github.com/user-attachments/assets/64fcd72a-7e36-4055-829c-d0ed4ecc9ef4)

# OUTPUT WAVEFORM:

![Screenshot 2024-11-14 050733](https://github.com/user-attachments/assets/e65d604a-9cc9-4845-acec-dc45266c97d8)

# RESULT:

Thus The Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.
