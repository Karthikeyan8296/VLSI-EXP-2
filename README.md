
DATE-

SIMULATION AND IMPLEMENTATION OF COMBINATIONAL

CIRCUITS



AIM: To simulate and synthesis ENCODER, DECODER, MULTIPLEXER, DEMULTIPLEXER, MAGNITUDE COMPARATOR using Vivado.



APPARATUS REQUIRED: VIVADO 2023.2



PROCEDURE:

STEP:1 Start the Vivado, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the Behavioural Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.
 
ENCODER:
![image](https://github.com/Karthikeyan8296/VLSI-EXP-2/assets/165583967/dcc1b757-5e53-4d85-b8e0-849984d3646a)
























PROGRAM:

module encoder (d, a0, a1, a2);

input [7:0] d;

output a0, a1, a2;

assign a2=d[7] |d[6] |d[5] |d[4];

assign a1=d[7] |d[6] |d[3] |d[2];

assign a0=d[7] |d[5] |d[3] |d[1];

endmodule

OUTPUT:
![image](https://github.com/Karthikeyan8296/VLSI-EXP-2/assets/165583967/ec1bf16a-0d2f-4ffe-a698-e916a7662f44)


 
 
DECODER:
![image](https://github.com/Karthikeyan8296/VLSI-EXP-2/assets/165583967/08695617-316a-4ca1-8bf5-5f0856eac60e)


























PROGRAM:

module decoder (s, y);

input [2:0] s;

output [7:0] y;

assign y[0]=~s[2] & ~s[1] & ~s[0];

assign y[1]=~s[2] &~s[1] & s[0];

assign y[2]=~s[2] & s[1] &~s[0];

assign y[3]=~s[2] & s[1] & s[0];

assign y[4]=s[2] & ~s[1] & ~s[0];

assign y[5]=s[2] & ~s[1] & s[0];

assign y[6]=s[2] & s[1] & ~s[0];

assign y[7]=s[2] & s[1] & s[0];

endmodule
 
OUTPUT:
![image](https://github.com/Karthikeyan8296/VLSI-EXP-2/assets/165583967/27bab166-72a3-47b7-ac73-8eb73350e52a)



























MULTIPLEXER:
![image](https://github.com/Karthikeyan8296/VLSI-EXP-2/assets/165583967/0e472598-3f02-40f5-924d-271192c48353)



 
PROGRAM:

module Mux_8_1(s0,s1,s2,i,y);

input [7:0] i;

input s0, s1, s2;

output y;

wire [7:0] w;

assign w[0]=(~s2) & (~s1) & (~s0) & i[0];

assign w[1]=(~s2) &(~s1) &(s0) & i[1];

assign w[2]=(~s2) &(s1) &(~s0) & i[2];

assign w[3]=(~s2) &(s1) &(s0) & i[3];

assign w[4]=(s2) &(~s1) &(~s0) & i[4];

assign w[5]=(s2) &(~s1) &(s0) & i[5];

assign w[6]=(s2) &(s1) &(~s0) & i[6];

assign w[7]=(s2) &(s1) &(s0) & i[7];

assign y=w[0] |w[1] |w[2] |w[3] |w[4] |w[5] |w[6] |w[7]; endmodule


OUTPUT:
![image](https://github.com/Karthikeyan8296/VLSI-EXP-2/assets/165583967/4c48b008-8634-45f9-a741-618d60584faf)


 
 
DEMULTIPLEXER:
![image](https://github.com/Karthikeyan8296/VLSI-EXP-2/assets/165583967/a42b55bb-0a61-4908-b1fc-cf7f350cf11d)































PROGRAM:

module Demux1_8(i, s0, s1, s2, y);

input i;

input s0, s1, s2;

output [7:0] y;

assign y[0]=~s0 &~s1 &~s2 & i;

assign y[1]=~s0 &~s1 &s2 & i;

assign y[2]=~s0 &s1 &~s2 & i;

assign y[3]=~s0 &s1 &s2 & i;

assign y[4]=s0 & ~s1 & ~s2 & i;

assign y[5]=s0 & ~s1 & s2 & i;

assign y[6]=s0 & s1 & ~s2 & i;

assign y[7]=s0 & s1 &s2 & i;

endmodule
 
OUTPUT:
![image](https://github.com/Karthikeyan8296/VLSI-EXP-2/assets/165583967/3f65074a-9825-47cc-b128-eb5254d9fbf8)

































MAGNITUDE COMPARATOR:
![image](https://github.com/Karthikeyan8296/VLSI-EXP-2/assets/165583967/499db745-01da-4204-a3a6-de79100b0bcd)






















PROGRAM:

module mag_cmp(a,b,l,g,e);

input [3:0]a,b;

output reg l,g,e;

always @(*)
 
begin

if(a>b)

begin

l=1'b0;

g=1'b1;

e=1'b0;

end

else if(a<b)

begin

l=1'b1;

g=1'b0;

e=1'b0;

end

else

begin

l=1'b0;

g=1'b0;

e=1'b1;

end

end

endmodule
 


OUTPUT:
![image](https://github.com/Karthikeyan8296/VLSI-EXP-2/assets/165583967/4aa0540d-7b1a-4393-bf60-9061c5077f01)



















































RESULT:

Thus, the combinational circuits of multiplexer, demultiplexer, encoder, decoder and magnitude comparator are implemented and simulated successfully.
