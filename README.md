# SR-FLIPFLOP-USING-CASE

**AIM:**

To implement  SR flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

SR Flip-Flop SR flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.

![image](https://github.com/sanjevrm/SR-FLIPFLOP-USING-CASE/assets/155142423/ef27add0-47aa-46ff-a084-c622688d02a6)


 
This circuit has two inputs S & R and two outputs Qtt & Qtt’. The operation of SR flipflop is similar to SR Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable. The following table shows the state table of SR flip-flop.

![image](https://github.com/sanjevrm/SR-FLIPFLOP-USING-CASE/assets/155142423/3c26b6bb-166b-41ce-90a2-56e7e05f516c)


 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, SR flip-flop can be used for one of these three functions such as Hold, Reset & Set based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of SR flip-flop. Present Inputs Present State Next State

![image](https://github.com/sanjevrm/SR-FLIPFLOP-USING-CASE/assets/155142423/a5000f35-75ad-4cbc-8554-52cd58e0bb12)


 
By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. The three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

![image](https://github.com/sanjevrm/SR-FLIPFLOP-USING-CASE/assets/155142423/4c241312-3029-49b0-8eb5-ec1832789a1a)


 
The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=S+R′Q(t)Q(t+1)=S+R′Q(t)

**Procedure**

1.Type the program in Quartus software.

2.Compile and run the program.

3.Generate the RTL schematic and save the logic diagram.

4.Create nodes for inputs and outputs to generate the timing diagram.

5.For different input combinations generate the timing diagram.


**PROGRAM**

```
Program for flipflops and verify its truth table in quartus using Verilog programming.
Developed by: Sanjev R M
RegisterNumber:212223040186
```
```verilog
module EXP_6(q, q_bar, s,r, clk, reset);//SR Flip Flop Behavioral Level using ‘case’ 
  input s,r,clk, reset;
  output reg q;
  output q_bar;
 
  always@(posedge clk) begin // for synchronous reset
    if(!reset)       
			q <= 0;
    else 
  begin
      case({s,r})       
	     2'b00: q <= q;    // No change
        2'b01:q<=1'b0;   // Write logic for reset
        2'b10:q<=1'b1;   // Write logic for set
        2'b11:q<=1'bx;   // Write logic for Invalid state
      endcase
    end
  end
  assign q_bar = ~q;
endmodule
```
**RTL LOGIC FOR FLIPFLOPS**
![image](https://github.com/sanjevrm/SR-FLIPFLOP-USING-CASE/assets/155142423/6a99dec6-9d0f-49f4-89b7-bf3c504b4bbe)




**TIMING DIGRAMS FOR FLIP FLOPS**
![image](https://github.com/sanjevrm/SR-FLIPFLOP-USING-CASE/assets/155142423/63766b6a-feb6-493c-8166-97118ff58337)




**RESULTS**
The observation of the simulation results and confirm the successful execution of the program.

