# NAME:VESHWANTH
# REG NO:212224230300
# 4-BIT-RIPPLE-COUNTER
# DATE:02-11-2025
**AIM:**

To implement  4 Bit Ripple Counter using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 Bit Ripple Counter**

A binary ripple counter consists of a series connection of complementing flip-flops (T or JK type), with the output of each flip-flop connected to the Clock Pulse input of the next higher-order flip-flop. The flip-flop holding the least significant bit receives the incoming count pulses. The diagram of a 4-bit binary ripple counter is shown in Fig. below.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/cb4b74d4-31ab-4359-95d0-d22e67daba13)

In timing diagram Q0 is changing as soon as the negative edge of clock pulse is encountered, Q1 is changing when negative edge of Q0 is encountered(because Q0 is like clock pulse for second flip flop) and so on.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/a573a7d6-014e-4e54-93e6-e2ac9530960b)

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/85e1958a-2fc1-49bb-9a9f-d58ccbf3663c)

**Procedure**

1.Ripple counter = asynchronous counter; each flip-flop is clocked by the previous one.
2.Declare clk, rstn (inputs) and q[3:0] (4-bit output).
3.Triggered by external clock — toggles on every rising edge of clk
4.Each triggered by falling edge of the previous flip-flop output.
5.Apply active-low reset (rstn = 0) to clear all outputs to 0.
6.Close the design with endmodule.
7.Run in simulator — ensure q counts 0000 → 1111 → 0000.

**PROGRAM**

    /* Program for 4 Bit Ripple Counter and verify its truth table in quartus using Verilog programming.

    module RIPPER (clk, rstn, q);
    input clk, rstn;       
    output [3:0] q;        
    reg [3:0] q;
    
    always @(posedge clk or negedge rstn)
        if (!rstn)
        q[0] <= 0;
        else
        q[0] <= ~q[0];
    always @(negedge q[0] or negedge rstn)
        if (!rstn)
        q[1] <= 0;
        else
        q[1] <= ~q[1];
    always @(negedge q[1] or negedge rstn)
        if (!rstn)
        q[2] <= 0;
        else
        q[2] <= ~q[2];

    always @(negedge q[2] or negedge rstn)
        if (!rstn)
        q[3] <= 0;
        else
        q[3] <= ~q[3];

    endmodule


    */

**RTL LOGIC FOR 4 Bit Ripple Counter**

<img width="1917" height="1148" alt="RTL" src="https://github.com/user-attachments/assets/8fd8bbfb-6171-41b4-8eb3-617afce5997b" />


**TIMING DIGRAMS FOR 4 Bit Ripple Counter**

<img width="1912" height="1137" alt="TIMING DIAGRAM" src="https://github.com/user-attachments/assets/7f9bdc10-eef5-4f7f-90f4-28c38adee2dd" />


**RESULTS**

The given 4Bit Ripper of asychronous Counter is successfully implemented using the Verilog HDL in the Quartus Prime.
