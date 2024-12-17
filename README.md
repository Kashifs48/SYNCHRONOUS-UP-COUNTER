SYNCHRONOUS-UP-COUNTER


AIM:

To implement 4 bit synchronous up counter and validate functionality.

SOFTWARE REQUIRED:

Quartus prime

4 bit synchronous UP Counter

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/user-attachments/assets/5faf014c-12d1-4985-bbd0-b972031ac691)


![image](https://github.com/user-attachments/assets/9ebedeea-1da0-4003-9ef2-e65a3f0be9ce)


Each flip-flop in this circuit will be clocked at exactly the same time. The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.” Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse. Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time. The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed. However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

Procedure

1.Initialize the shift register to a known state (e.g., all zeros).

2.Input a bit serially into the shift register.

3.Shift the contents of the register one position to the right (or left).

4.Output the shifted bit from the last stage of the register.

5.Repeat steps 2-4 for each bit you want to input and shift.

PROGRAM

module ex11(out,clk,rstn);

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

RTL LOGIC UP COUNTER

![image](https://github.com/user-attachments/assets/f0bbdacc-9d73-4442-bc49-297ffcb135eb)


TIMING DIAGRAM FOR IP COUNTER

![image](https://github.com/user-attachments/assets/2b773833-5561-4478-932a-992c3dd8c7ac)


TRUTH TABLE

![image](https://github.com/user-attachments/assets/fd9d6f1c-879d-40fc-877a-a37af46eae20)


Developed by:SYED KASHIF S

RegisterNumber:24006084

RESULTS

Hence a 4 bit synchronous up counter is implemented correctly.
