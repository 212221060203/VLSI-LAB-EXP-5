# VLSI-LAB-EXP-5
SIMULATION AND IMPLEMENTATION OF FINITE STATE MACHINE

## AIM: 

To simulate and synthesis finite state machine using Xilinx ISE.

**APPARATUS REQUIRED: **
vivado 2023.2.

## PROCEDURE: **
STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation and then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table.
STEP:11 On the board, by giving required input, the LEDs starts to glow light, indicating the output.
STEP:12 Load the Bit file into the SPARTAN 6 FPGA 

Logic Diagram :

![image](https://github.com/navaneethans/VLSI-LAB-EXP-5/assets/6987778/34ec5d63-2b3b-4511-81ef-99f4572d5869)

## VERILOG CODE:
VERILOG CODE:
module fsm(clk, rst, x, z);

input clk, rst, x;

output z;

reg [2:1] present_state, NEXT_STATE;

parameter S0=2'b00, S1=2'b01, S2=2'b10, S3=2'b11;

always@(x,present_state)

case(present_state)

S0: if(x)

NEXT_STATE=S1;

else

NEXT_STATE=S0;

S1: if(x)

NEXT_STATE=S1;

else

NEXT_STATE=S2;

S2: if(x)

NEXT_STATE=S3;

else

NEXT_STATE=S0;

S3: if(x)

NEXT_STATE=S1;

else

NEXT_STATE=S2;

endcase

always@(negedge rst, posedge clk)

if(rst)

present_state<=S0;

else

present_state<=NEXT_STATE;

assign z=(present_state==S3);

endmodule

## OUTPUT:

![image](https://github.com/212221060203/VLSI-LAB-EXP-5/assets/166364913/3ef06601-1772-40be-b05b-0e4bc3454974)
## RESULT:
Thus,the simulation and synthesis of finite state machine by using vivado has been successfully excecuted and verified.
