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

/* write all the steps invloved */

**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming.

Developed by: Haresh R
RegisterNumber: 24901004

*/
 module siso_shift_register (
    input clk,    
    input reset, 
    input si,     
    output reg so 
);
    reg [3:0] shift_reg; 
    always @(posedge clk or posedge reset) begin
        if (reset) begin
            shift_reg <= 4'b0000; 
            so <= 0;            
        end
        else begin
            so <= shift_reg[3];              
RTL LOGIC FOR SISO Shift Register
 TIMING DIGRAMS FOR SISO Shift Register
 RESULTS thus the output was successfully verified.
            shift_reg <= {shift_reg[2:0], si}; 
        end
    end
 endmodule

**RTL LOGIC FOR SISO Shift Register**
![Screenshot 2024-12-27 145710](https://github.com/user-attachments/assets/67ea64c8-b46c-405d-8f65-5bc5bde807cc)


**TIMING DIGRAMS FOR SISO Shift Register**
![Screenshot 2024-12-27 145729](https://github.com/user-attachments/assets/f8d7359e-5bf4-4688-9b3e-bfb6d84eb7b4)

**RESULTS**
thus the output was successfully verified.
