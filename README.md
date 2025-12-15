# Upcounter
AIM:

To implement 4 bit synchronous up counter and validate functionality.

SOFTWARE REQUIRED:

Quartus prime

THEORY

4 bit synchronous UP Counter

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

<img width="502" height="275" alt="image" src="https://github.com/user-attachments/assets/e8546c42-61a7-46b5-947d-77b35e6c0447" />

<img width="602" height="328" alt="image" src="https://github.com/user-attachments/assets/991bbb28-2f22-4580-b0bb-e785c6facc79" />

Each flip-flop in this circuit will be clocked at exactly the same time. The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.” Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse. Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time. The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed. However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

#Procedure
Decide the number of bits and identify the clock and output lines.

Use flip-flops (JK or T) with all clocks connected to a common clock.

Configure the first flip-flop to toggle on every clock pulse.

Design the logic so each higher flip-flop toggles when all lower bits are high.

Simulate and verify correct binary counting on each clock edge.

#PROGRAM
```
module Upcounter (out,clk,rstn);
input clk,rstn;
output reg [3:0]out;
always @ (posedge clk)
begin
   if(!rstn)
     out<=0;
   else 
     out <= out+1;
end
endmodule
```
Developed by: VANATHI T

RegisterNumber: 25013590

RTL LOGIC UP COUNTER
<img width="1920" height="1020" alt="Screenshot 2025-12-15 202123" src="https://github.com/user-attachments/assets/2a9a0cd4-2939-47b2-bb46-5d7988ae87f4" />

TIMING DIAGRAM FOR IP COUNTER

TRUTH TABLE

RESULT: 
Implemented 4 bit synchronous up counter and validate functionality.

