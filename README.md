# SR-FLIPFLOP-USING-CASE

**AIM:**

To implement  SR flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

SR Flip-Flop SR flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/0f710028-ad52-4d3e-9276-8714cf023a25)

 
This circuit has two inputs S & R and two outputs Qtt & Qtt’. The operation of SR flipflop is similar to SR Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable. The following table shows the state table of SR flip-flop.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/dabfc4f4-87e3-4cbc-9472-f89ee1b5ed30)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, SR flip-flop can be used for one of these three functions such as Hold, Reset & Set based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of SR flip-flop. Present Inputs Present State Next State

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/dd90d16c-aec5-4290-a586-e2346b1e9eb5)

 
By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. The three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/473efad6-d70b-4ca7-aeb7-898bbfca319f)

 
The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=S+R′Q(t)Q(t+1)=S+R′Q(t)

**Procedure**

1.Type the program in Quartus software.

2.Compile and run the program.

3.Generate the RTL schematic and save the logic diagram.

4.Create nodes for inputs and outputs to generate the timing diagram.

5.For different input combinations generate the timing diagram.

**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming.
Developed by: M . VIRUMAA HARISH
RegisterNumber: 212223230246
*/
module SR_FLIPFLOP(q, q_bar, s,r, clk, reset);//SR Flip Flop Behavioral Level using ‘case’ 
  input s,r,clk, reset;
  output reg q;
  output q_bar;
 
  always@(posedge clk) begin // for synchronous reset
    if(!reset)       q <= 0;
    else 
  begin
      case({s,r})       
	     2'b00: q <= q;    // No change
        2'b01: q <= 1'b0; // Write logic for reset
        2'b10: q <= 1'b1; // Write logic for set
        2'b11: q <= 1'bx; // Write logic for Invalid state
      endcase
    end
  end
  assign q_bar = ~q;
endmodule


**RTL LOGIC FOR FLIPFLOPS**

![Screenshot 2024-05-13 170710](https://github.com/Virumaaharish/SR-FLIPFLOP-USING-CASE/assets/146074950/ffb3bd0e-0e24-4028-b721-065c81b2dfa8)


**TIMING DIGRAMS FOR FLIP FLOPS**

![Screenshot 2024-05-13 170756](https://github.com/Virumaaharish/SR-FLIPFLOP-USING-CASE/assets/146074950/026b8375-d5dc-40c8-8f10-83d253a045f5)


**RESULTS**

Thus the implemention of SR flipflop using verilog and the RTL,timing diagram are generated successfully.
