# SIMULATION OF LOGIC GATES, ADDERS AND SUBRACTORS USING VIVADO
AIM: 

To simulate and synthesis Logic Gates,Adders and Subtractor using vivado.

APPARATUS REQUIRED: 

Vivado 2023.1

PROCEDURE:

STEP:1 Start the Xilinx navigator, Select and Name the New project.

STEP:2 Select the device family, device, package and speed. 

STEP:3 Select new source in the New Project and select Verilog Module as the Source type. 

STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it. 

STEP:5 Select the Behavioral Simulation in the Source Window and click the check syntax. 

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table. 

STEP:7 Select the Implementation in the Sources Window and select the required file in the Processes Window. 

STEP:8 Select Check Syntax from the Synthesize XST Process. Double Click in the Floorplan Area/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained. 

STEP:9 In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu. 

STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into 
.bit file here. 

STEP:11 Load the Bit file into the SPARTAN 6 FPGA 

STEP:12 On the board, by giving required input, the LEDs starts to glow light, indicating the output.

Logic Diagram :

Logic Gates:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/ee17970c-3ac9-4603-881b-88e2825f41a4)


Half Adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/0e1ecb96-0c25-4556-832b-aeeedfdfe7b9)


Full adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/9bb3964c-438f-469d-a3de-c1cca6f323fb)


Half Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/731470b7-eb4e-49f8-8bb7-2994052a7184)


Full Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/d66f874b-c1f2-44b3-a035-7149b56430c1)


8 Bit Ripple Carry Adder

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/7385a408-40a5-4203-8050-b72818622d79)


# LOGIC GATES

VERILOG CODE :
```
module logicgates(a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate);
input a,b;
output andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate;
and(andgate,a,b);
or(orgate,a,b);
xor(xorgate,a,b);
nand(nandgate,a,b);  
nor(norgate,a,b);
xnor(xnorgate,a,b);
not(notgate,a);
endmodule
```

OUTPUT:

![329837343-8adead73-cb3a-494c-bbcc-29316d72f2e8](https://github.com/gladsinpaul/VLSI-LAB-EXP-1/assets/117917349/fb2b2c70-bb34-41d2-b9ba-0754455eb803)

![329837360-7364d19f-984a-434b-9e31-9c5e3c075b30](https://github.com/gladsinpaul/VLSI-LAB-EXP-1/assets/117917349/fcb55ab3-0d52-455c-a1a7-a7281c235203)




# HALF ADDER
VERILOG CODE :
```
module half_adder(a,b,sum,carry);
input a,b;
output sum,carry; 
or(sum,a,b);
and(carry,a,b);
endmodule
```

OUTPUT:

![329837398-f0e86ac2-d8dd-494b-a221-68d7b9a5b15f](https://github.com/gladsinpaul/VLSI-LAB-EXP-1/assets/117917349/4b1737ce-d6cf-4bae-9e74-0d17da2976ad)


![329837420-b4bd0f00-7347-426a-838d-9d3e01fc366a](https://github.com/gladsinpaul/VLSI-LAB-EXP-1/assets/117917349/b4baae21-1280-4ac4-9b80-7e4cf6e27a8d)


# FULL ADDER

VERILOG CODE :
```
module fa_ha(a,b,c,sum,cout);
input a,b,c;
output sum,cout;
wire wl, w2, w3, w4, w5;
xor x1(w1,a,b);
xor x2 (sum,w1,c) ;
and al(w2,a,b) ;
and a2(w3,b,c);
and a3(w4,a,c) ;
or o1(w5,w2,w3) ;
or o2(cout,w5,w4) ;
endmodule
```

OUTPUT :
![329837452-2681a414-03c8-4168-9b81-953787bb330d](https://github.com/gladsinpaul/VLSI-LAB-EXP-1/assets/117917349/4fc7c87a-b046-4a26-8bc8-6be4960bad97)

![329837482-20675a21-88b7-4ddc-9219-d52279ae208d](https://github.com/gladsinpaul/VLSI-LAB-EXP-1/assets/117917349/780964f8-93fd-4244-b44a-ee103994915d)



# HALF SUBRACTOR

VERILOG CODE :
```
module halfsubtractor( D,Bo,A,B);
input A,B;
output D,Bo;
wire w1;
xor (D,A,B);
not (w1,B);
and (Bo,B,w1);
endmodule
```

OUTPUT:
![329837506-4a09d52e-e9a7-46b4-9da6-71dde108e03b](https://github.com/gladsinpaul/VLSI-LAB-EXP-1/assets/117917349/f6ad669b-7888-4b9b-af8e-a0b3ccc2f475)

![329837532-5b497c5e-24a7-44f1-9ff7-4e2766815897](https://github.com/gladsinpaul/VLSI-LAB-EXP-1/assets/117917349/eefe08d2-da9d-4c2e-8e1a-969d878b38a6)



# FULL SUBRACTOR

VERILOG CODE :
```
module full_sub(borrow,diff,a,b,c);
output borrow,diff;
input a,b,c;
wire w1,w4,w5,w6;
xor (diff,a,b,c);
not n1(w1,a);
and a1(w4,w1,b);
and a2(w5,w1,c);
and a3(w6,b,c);
or o1(borrow,w4,w5,w6);
endmodule
```

OUTPUT :

![329837565-08a70f1e-01eb-4546-b875-a0bc47e65266](https://github.com/gladsinpaul/VLSI-LAB-EXP-1/assets/117917349/fb8998e2-7d7a-4225-a195-2bbba0075e4e)

![329837578-95711206-eb3f-4dbb-855a-413ed83f025f](https://github.com/gladsinpaul/VLSI-LAB-EXP-1/assets/117917349/5a70a7ab-8a8a-48ac-a588-c6d9fa3589ad)




# RIPPLECARRYADDER 4_Bit

VERILOG CODE :
```
module ripplemod(a, b, cin, sum, cout);
input [07:0] a;
input [07:0] b;
input cin;
output [7:0]sum;
output cout;
wire[6:0] c;
fulladd a1(a[0],b[0],cin,sum[0],c[0]);
fulladd a2(a[1],b[1],c[0],sum[1],c[1]);
fulladd a3(a[2],b[2],c[1],sum[2],c[2]);
fulladd a4(a[3],b[3],c[2],sum[3],c[3]);
fulladd a5(a[4],b[4],c[3],sum[4],c[4]);
fulladd a6(a[5],b[5],c[4],sum[5],c[5]);
fulladd a7(a[6],b[6],c[5],sum[6],c[6]);
fulladd a8(a[7],b[7],c[6],sum[7],cout);
endmodule
module fulladd(a, b, cin, sum, cout);
input a;
input b;
input cin;
output sum;
output cout;
assign sum=(a^b^cin);
assign cout=((a&b)|(b&cin)|(a&cin));
endmodule
```

OUTPUT :

![329837606-018782bf-1b8d-4025-8a47-ff517eeffd52](https://github.com/gladsinpaul/VLSI-LAB-EXP-1/assets/117917349/70dc4a2f-37fb-438d-85e1-0f09c52cf552)

![329837633-ac19799c-2464-4e79-aa87-a09c95d50d84](https://github.com/gladsinpaul/VLSI-LAB-EXP-1/assets/117917349/69e620e0-1ff2-4542-9ed4-4005ec9da28d)




# RIPPLECARRYADDER 8_Bit

VERILOG CODE :
```
module ripplemod(a, b, cin, sum, cout);
input [07:0] a;
input [07:0] b;
input cin;
output [7:0]sum;
output cout;
wire[6:0] c;
fulladd a1(a[0],b[0],cin,sum[0],c[0]);
fulladd a2(a[1],b[1],c[0],sum[1],c[1]);
fulladd a3(a[2],b[2],c[1],sum[2],c[2]);
fulladd a4(a[3],b[3],c[2],sum[3],c[3]);
fulladd a5(a[4],b[4],c[3],sum[4],c[4]);
fulladd a6(a[5],b[5],c[4],sum[5],c[5]);
fulladd a7(a[6],b[6],c[5],sum[6],c[6]);
fulladd a8(a[7],b[7],c[6],sum[7],cout);
endmodule
module fulladd(a, b, cin, sum, cout);
input a;
input b;
input cin;
output sum;
output cout;
assign sum=(a^b^cin);
assign cout=((a&b)|(b&cin)|(a&cin));
endmodule
```

OUTPUT :

![329837652-11ddb80b-c7df-4717-9092-156a8a8b5778](https://github.com/gladsinpaul/VLSI-LAB-EXP-1/assets/117917349/1cbd5f47-7dc4-4da5-85f3-609531f28c87)

![329837664-dc75f3a8-5c8f-4ed4-9254-bf3025a93237](https://github.com/gladsinpaul/VLSI-LAB-EXP-1/assets/117917349/9e2de8a4-2d8c-44f8-962f-9e20e8113c0b)

RESULT:
Thus the simulation of Logic Gates, Adders and Subtractor is completed using Vivado.
