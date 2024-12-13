### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![Screenshot 2024-12-13 235155](https://github.com/user-attachments/assets/02ee9398-9225-42ea-a6eb-43ab6b50eb9b)

![Screenshot 2024-12-13 235205](https://github.com/user-attachments/assets/fc287bf5-6304-4519-abf3-3e686cb0ecce)

The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**

1.Initialize the shift register to a known state (e.g., all zeros).

2.Input a bit serially into the shift register.

3.Shift the contents of the register one position to the right (or left).

4.Output the shifted bit from the last stage of the register.

5.Repeat steps 2-4 for each bit you want to input and shift.

**PROGRAM**
```
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
```

 

Developed by:KAILAN P
RegisterNumber: 24900859
*/

**RTL LOGIC UP COUNTER**

![Screenshot 2024-12-13 235217](https://github.com/user-attachments/assets/714fe03b-e6e8-4316-8fdb-c3fb783a5f55)


**TIMING DIAGRAM FOR IP COUNTER**

![Screenshot 2024-12-13 235231](https://github.com/user-attachments/assets/aede3642-f648-4c7c-8dd9-8bfd131a7392)


![Screenshot 2024-12-13 235245](https://github.com/user-attachments/assets/0809fc33-122e-41a6-88aa-9b09e157dcca)


**RESULTS**

Hence a 4 bit synchronous up counter is implemented correctly
