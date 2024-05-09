# SERIAL-IN-SERIAL-OUT-SHIFTREGISTER

**AIM:**

To implement  SISO Shift Register using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**SISO shift Register**

A Serial-In Serial-Out shift register is a sequential logic circuit that allows data to be shifted in and out one bit at a time in a serial manner. It consists of a cascade of flip-flops connected in series, forming a chain. The input data is applied to the first flip-flop in the chain, and as the clock pulses, the data propagates through the flip-flops, ultimately appearing at the output.

The logic circuit provided below demonstrates a serial-in serial-out (SISO) shift register. It comprises four D flip-flops that are interconnected in a sequential manner. These flip-flops operate synchronously with one another, as they all receive the same clock signal.

![image](https://github.com/naavaneetha/SERIAL-IN-SERIAL-OUT-SHIFTREGISTER/assets/154305477/e81c4072-37f9-46c6-8145-566764b74c3a)

Figure 01 4 Bit SISO Register

The synchronous nature of the flip-flops ensures that the shifting of data occurs in a coordinated manner. When the clock signal rises, the input data is sampled and stored in the first flip-flop. On subsequent clock pulses, the stored data propagates through the flip-flops, moving from one flip-flop to the next.
Each D flip-flop in the circuit has a Data (D) input, a Clock (CLK) input, and an output (Q). The D input represents the data to be loaded into the flip-flop, while the CLK input is connected to the common clock signal. The output (Q) of each flip-flop is connected to the D input of the next flip-flop, forming a cascade.

**Procedure**
1.Define Module: Define a Verilog module for the T flip-flop with inputs (T, CLK) and outputs (Q, Q_bar).

2.Declare Inputs and Outputs: Declare input and output ports for the module.

3.Implement Flip-Flop Logic: Write Verilog code to implement the T flip-flop logic based on its functional table. Use a synchronous always @(posedge CLK) block to trigger the flip-flop on the positive edge of the clock signal.

4.Simulate Using Testbench: Write a Verilog testbench to simulate the behavior of the T flip-flop under different input conditions.

5.Apply Input Stimuli: In the testbench, apply various combinations of input stimuli (T, CLK) to cover all possible input states.

6.Verify Output Behavior: Verify that the output behavior of the T flip-flop matches the expected behavior defined by its functional table.

7.Check for Race Conditions: Ensure that there are no race conditions or undefined states in the design by analyzing the timing and sequence of input changes.

**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming.

Developed by: KANIMOZHI
RegisterNumber: 212222230060

*/
```
module ex09( input clk, rst_n, input t, 
output reg q, 
output q_bar 
); 
always@(posedge clk) 
begin // for synchronous reset 
 //WRITE THE CONDITION OF TOGGLE FLIPFLOP HERE WITH RESET AND 
 //IMPLEMENT THE T LOGIC BY CONDITIONAL OPERATOR 
if(!rst_n) 
q<=0; 
else 
begin 
q<=(t?~q:q); 
end 
end 
assign q_bar = ~q; 
endmodule
```

**RTL LOGIC FOR SISO Shift Register**
![326266966-4c5b38ef-1f5e-41c7-8914-2a46995a9e3f](https://github.com/kanimozhipannerselvam/SERIAL-IN-SERIAL-OUT-SHIFTREGISTER/assets/119476060/86b8b1cf-0767-4d0c-859c-9a84878fe1a4)



**TIMING DIGRAMS FOR SISO Shift Register**

![326266993-4ed93a13-97e0-4672-8b13-bd18d377a300](https://github.com/kanimozhipannerselvam/SERIAL-IN-SERIAL-OUT-SHIFTREGISTER/assets/119476060/ebe67859-6816-44e1-8d37-15f084995506)



**RESULTS**
Hence, T flipflop using verilog and validating their functionality using their functional tables is implemented.

