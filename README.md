# VHDL5
A Full Subtractor is a combinational logic circuit used to perform subtraction of three bits: two significant bits and a borrow from the previous stage. <br>
It computes the difference and the borrow based on these inputs.<br>
Outputs: Difference: Represents the result of A - B - Bin. <br>
Borrow: Indicates if borrow is required for the next stage of subtraction.<br>

`Aim:`<br>
To design and implement a Full Subtractor using Verilog HDL and verify its functionality through simulation. <br>

`Apparatus Required:` <br>

-Xilinx Vivado (or any Verilog simulator). <br>
-PC/Laptop with required software tools. <br>

`Code Implementation:` <br>

#Dataflow Model:
In this model, the circuit is described using logical expressions. The dataflow model relies on assign statements to represent the logical flow of data.

module full_subtractor_dataflow(input a, input b, input bin, output diff, output bout);<br>
  assign diff = a ^ b ^ bin;<br>
  assign bout = (~a & b) | (b & bin) | (~a & bin);<br>
endmodule<br>

#Behavioral Model: 
The behavioral model uses an always block to describe the functionality of the Half Adder at an abstract level. It mimics how the circuit behaves without specifying exact hardware.

module full_subtractor_behavioral(input a, input b, input bin, output reg diff, output reg bout);<br>
  always @(*) begin<br>
    diff = a ^ b ^ bin;<br>
    bout = (~a & b) | (b & bin) | (~a & bin);<br>
  end<br>
endmodule<br>

#Structural Model:
The structural model is a low-level description where the design is expressed using basic logic gates (AND, XOR). This is closest to actual hardware representation.

module full_subtractor_behavioral(input a, input b, input bin, output reg diff, output reg bout);<br>
  always @(*) begin<br>
    diff = a ^ b ^ bin;<br>
    bout = (~a & b) | (b & bin) | (~a & bin);<br>
  end<br>
endmodule<br>

![WhatsApp Image 2024-10-15 at 17 54 12_f0bb7821](https://github.com/user-attachments/assets/445e0b0d-4d57-4c00-8f82-186c555d01d8)


`Output Waveform:`

![WhatsApp Image 2024-10-15 at 17 50 52_5f1514d2](https://github.com/user-attachments/assets/0712044e-bd1a-4c82-a36c-94f3ce21caf1)


`Result:`

The Full Subtractor circuit was successfully implemented using Dataflow, Behavioral, and Structural modeling approaches in Verilog, and the simulation results were validated against the expected output.



