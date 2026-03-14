# JKFLIPFLOP-USING-IF-ELSE

**AIM:** 

To implement  JK flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**JK Flip-Flop**

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/a649c30b-232b-4558-b188-fd6c09845180)


This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/c4360742-e8a8-4937-b089-c46c0433f9a3)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/6c275261-a6d5-4c37-a3a7-1e88ca11c4cd)

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/5174f41b-0ce0-4329-a372-6d1943ea6673)

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

**Procedure**

1.Define Inputs/Outputs: Inputs: J (Set), K (Reset), c1k (clock); Outputs: q, qbar (~q).
2.Initialization: Set q = 0 and qbar = 1 at the start of the simulation.
3.JK Flip-Flop Logic: On posedge c1k, compute q
4.Complementary Output: Update qbar = ~q to maintain complementarity.
5.Testbench: Simulate with combinations of J, K, and c1k to verify JK Flip-Flop functionality.

**PROGRAM**

 Program for flipflops and verify its truth table in quartus using Verilog programming. 
 ~~~
 Developed by: A. KARTHIK
 RegisterNumber: 212225220049

 ~~~
 ~~~
 module jk_ff(q, qb,j,k,clock,reset);
    input j,k,clock,reset;
    output reg q, qb;
	 
always @ (posedge (clock))

    begin 
        if (!reset)
            begin
               q <= q;
               qb <=qb;
            end   
        
else
 //Write logic for JK flipflop using if else statement for four conditions

begin
               if (j == 0 && k == 0)
                    begin
                    q <= q;
                    qb <= qb;
                    end 
		else if (j != k)
                    begin
                    q <= j;
                    qb <= k;
                    end
               else if (j == 1 && k == 1) 
                    begin 
                    q <= ~q; 
                    qb <= ~qb; 
                    end 
            end
end  
endmodule

~~~


**RTL LOGIC FOR FLIPFLOPS**

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/1bc275e0-93c8-4edf-ac65-145a8c8fef80" />


**TIMING DIGRAMS FOR FLIP FLOPS**

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c7b7e6c7-a1d4-4647-b0e8-b35349db2686" />


**RESULTS**

Thus the JK flipflop is implemented and verified.
