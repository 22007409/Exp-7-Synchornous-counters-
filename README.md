Developed by: V SANDHIYA

RegisterNumber:22007409



AIM: To implement 4 bit up and down counters and validate  functionality.


HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher


SOFTWARE REQUIRED:   Quartus prime


THEORY 


UP COUNTER 


The counter is a digital sequential circuit and here it is a 4 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down). 


The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle.
The Counter will be set to Zero when “reset” input is at logic high.
The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down.
The counter will count up when the “up_down” signal is logic high, otherwise count down


Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output.
The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence.
Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1:
Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.


Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.


Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.


The Q outputs of each flip-flop will serve as the respective binary bits of the final, four-bit count:

 
Four-bit “Up” Counter


![AA](https://user-images.githubusercontent.com/121559414/212625653-705f98d3-82a6-40f1-9a73-614f5c2aa452.png)


DOWN COUNTER 


As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.


This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.


![AB](https://user-images.githubusercontent.com/121559414/212625904-cab31f31-690f-4342-bb5d-13f449f6e727.png)


4-bit Count Down Counter


PROCEDURE


1.Create a new project in QuartusII software.  

2.Name the project as uc for upcounter and dc for down counter.  

3.Create a new verilog hdl file in the project file.  

4.Name the module as dc and uc for down counter and up counter.  

5.Within the module declare input and output variables.  

6.Create a loop using if-else with condition parameter as reset value.  

7.End the loop.  

8.End the module.



PROGRAM 

Program for flipflops  and verify its truth table in quartus using Verilog programming.
  
UP COUNTER
:

```
module UPCOUNTER(input clk,input reset,output[0:3]counter);  

reg[0:3] counter_up;  

always@(posedge clk or posedge reset)  

begin  

if(reset)  

counter_up<=4'd0;  

else  

counter_up<=counter_up+4'd1;  

end  

assign counter=counter_up;  

endmodule



DOWN COUNTER:


module DOWNCOUNTER(input clk,input reset,output[0:3]counter);  

reg[0:3] counter_down;  

always@(posedge clk or posedge reset)  

begin  

if(reset)  

counter_down<=4'd0;  

else  

counter_down<=counter_down-4'd1;  

end  

assign counter=counter_down;  

endmodule
```



RTL LOGIC UP COUNTER AND DOWN COUNTER

UP COUNTER:

![AC](https://user-images.githubusercontent.com/121559414/212638469-e09d7d10-8679-46f3-a504-779586aa42eb.png)


DOWN COUNTER:

![AD](https://user-images.githubusercontent.com/121559414/212638572-cf9785a0-4aa0-4378-a069-b3b2e4dc7d08.png)


TIMING DIGRAMS FOR COUNTER


UP COUNTER:

![AE](https://user-images.githubusercontent.com/121559414/212638781-cd65011f-f58d-4827-9500-a3214e63dfd7.png)


DOWN COUNTER:

![AF](https://user-images.githubusercontent.com/121559414/212638851-f73b4925-525e-4493-bb00-e9fcd0989cc3.png)


TRUTH TABLE


UP COUNTER:

![AG](https://user-images.githubusercontent.com/121559414/212639047-aa969186-2b79-4c78-956e-b1c40a62796b.png)


DOWN COUNTER:

![AH](https://user-images.githubusercontent.com/121559414/212639231-4f26266f-9ced-4ade-9d0c-fe18dbd5adaf.png)



RESULTS :

Thus Synchornous counters up counter and down counter circuit are studied and the truth table for different logic gates are verified.

