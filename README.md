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

![WhatsApp Image 2024-10-15 at 17 54 11_31323d72](https://github.com/user-attachments/assets/31641ac1-6e1a-4bdd-a39d-568b8aa7bb64)

`Output Waveform:`

![WhatsApp Image 2024-10-15 at 17 50 51_aef18896](https://github.com/user-attachments/assets/aa07109b-42a9-42b2-9270-c7c49ba863bf)

`Result:`

The Full Subtractor circuit was successfully implemented using Dataflow, Behavioral, and Structural modeling approaches in Verilog, and the simulation results were validated against the expected output.



