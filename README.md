# VLSI-HDP

<details><summary> DAY-0  </summary> 

 ## DAY-0 

### Installed 3 tools 

> Yosys

![Screenshot 2022-11-28 at 12 36 01 PM](https://user-images.githubusercontent.com/43700789/204221443-15077ff4-6a19-4b8e-b3c8-821b1cd0babd.png)


> OpenSTA

![Screenshot 2022-11-28 at 12 41 19 PM](https://user-images.githubusercontent.com/43700789/204221544-23cc55c9-8fe7-46a2-89b6-0aa16762eb3b.png)

> ngspice

![Screenshot 2022-11-28 at 12 33 57 PM](https://user-images.githubusercontent.com/43700789/204221644-f8da8de4-9884-473a-b2d8-a6a96e09ce5b.png)

</details>

<details><summary> DAY-1  </summary> 

> # Introduction to Verilog RTL design and Synthesis
 
### Intro to open-source simulator iverilog
 - Simulator 
 - Testbench
<img width="1259" alt="Screenshot 2022-11-28 at 1 33 35 PM" src="https://user-images.githubusercontent.com/43700789/204224989-86daa03e-847c-433c-bbc9-dbc2bd52e9cb.png">

### Installation of Iverilog and gtkwave using command line

### Introduction to Yosys and Logic synthesis
-  RTL to gate level translation 
-  We also understood how the design is converted into gates and the connections are made 
-  Brief about netlist and how it can be simulated in the Yosys
<img width="1277" alt="Screenshot 2022-12-02 at 6 36 36 PM" src="https://user-images.githubusercontent.com/43700789/205365752-d7be974c-d719-4dfb-836c-a212de500b64.png">

## Day-1 Lab

- Colned a repo from Kunalg123- Guithub and deployed it in Yosys. 
- We worked on good_mux and created a netlist using the tools mentioned 

> [Simplified netlist generated using Yosys]

<img width="936" alt="Screenshot 2022-12-02 at 10 50 44 PM" src="https://user-images.githubusercontent.com/43700789/205368211-430f816b-0ef5-4fe3-ad5d-593f7c35a043.png"> 

 </details>

<details><summary> DAY-2  </summary>  

# Timing libs, hierarchical vs flat synthesis and efficient flop coding styles
 
 > ## Intro to timing.libs
 This is an introduction about .lib files where it contains the data about differnt types of files and how they vary. The variatins also depends on few crucial factors such as area which can be directly propotionate to factors such as temperature, power and the process. 
 * Added a sample of gvim file containing the area and power leakage of **"SKY130_fd_sc_hd__a2111o"** gate.
<img width="727" alt="Screenshot 2022-12-05 at 6 50 47 PM" src="https://user-images.githubusercontent.com/43700789/205648160-80d9dd9c-a3d5-434d-a2a7-47ac1f1c3e7b.png">

 * <b>.lib</b> files provide lot more extensive data about the cells and it's hirearchial data.  
 
 >  ### Hierarchial synthesis vs Flat synthesis
 <img width="1246" alt="Screenshot 2022-12-05 at 7 49 21 PM" src="https://user-images.githubusercontent.com/43700789/205707481-a389a68a-36cf-4c74-8f03-b863833ee41c.png">

> ### Various Flop coding styles and optimization 
* Here we understood how flipflops work and the differnce between <b> Synchronous and Asynchronous Flipflops </b>
* How hardware optimization is so much more effective and effeicent than the tradtional software methods. 
<img width="1516" alt="Screenshot 2022-12-05 at 9 28 24 PM" src="https://user-images.githubusercontent.com/43700789/205711184-f3485d10-624c-4507-8028-30736e1b78a2.png">

</details>

<details><summary> DAY-3  </summary>  

# Day 3 - Combinational and sequential optmizations

> ## Introduction to optimization 
  - Constant propagation 
  - Boolean logic optimaization 
 
 ### Sequential logic optimization 
 - Basic 
 
   1.Sequential constant propagation 
 - Advanced [Not covered in lab]
 
   1.State optimisation 
 
   2.Retiming 
 
   3.Sequential logic cloning (Floor plan aware synthesis)
 
 ### Combinational Logics HW
   - Opt_Check4.v 
 <img width="1603" alt="Screenshot 2022-12-10 at 3 47 28 PM" src="https://user-images.githubusercontent.com/43700789/206849813-01f3c8b3-0bbf-4a86-aa02-d5290f4abb87.png">
 
   - Multiple_module_opt2.v
 <img width="840" alt="Screenshot 2022-12-10 at 3 53 05 PM" src="https://user-images.githubusercontent.com/43700789/206849998-c0ca84ad-62f1-4876-82e1-9e7864390354.png">
 
### Sequential logic optimizations
    - dff_const3.v
 <img width="829" alt="Screenshot 2022-12-10 at 4 37 09 PM" src="https://user-images.githubusercontent.com/43700789/206852030-7d6f22c9-2373-48a4-9408-19b12f63aee8.png">

 <b> We ended the day3 learning about sequential optimization for unsed outputs. It sates what all outputs dont have roles in determinig the primary outputs in logic will be optimized.<b/>
  
  </details>
 
 <details><summary> DAY-4  </summary>  
  

  # Day 4 - GLS, blocking vs non-blocking and Synthesis-Simulation mismatch
  
  ## Synthesis simulation mismatch
  
  A synthesis simulation mismatch can occur when the behavior of a design in simulation does not match the behavior of the synthesized design when implemented on hardware. This can happen for a variety of reasons, including:
  - Missing Sensitivity list
  - Blocking & Non-blocking assignments
  - Non standard verilog coding
  
  ## Blocking & Non-blocking 
  
  In Verilog, blocking statements are executed sequentially, in the order in which they appear in the code. Each statement is executed before the next one is executed.

On the other hand, non-blocking statements are used to update the values of variables at the end of a time step, rather than immediately. Non-blocking assignments are used to update variables asynchronously, which means that the new value is not assigned to the variable until the end of the current time step.
  
  It is important to note that blocking assignments have a higher precedence than non-blocking assignments, which means that if both types of assignments are used on the same variable, the blocking assignment will be executed first. In addition to this, it is preferd to use non-blocking statements for  implementing sequential circuits.
  
  > LAB 1
  Normal way
  ![Screenshot 2022-12-16 at 1 37 43 PM](https://user-images.githubusercontent.com/43700789/208052677-1e0ba691-f56b-46dc-ae24-c4416cda6948.png)
  
  With GLS 
  ![Screenshot 2022-12-16 at 1 49 09 PM](https://user-images.githubusercontent.com/43700789/208054546-1025e34a-0834-4277-9c01-183c955fc78e.png)
> LAB 2
  
  ### Bad_mux with and without Synthesis and GLS
  
![Screenshot 2022-12-16 at 2 01 45 PM](https://user-images.githubusercontent.com/43700789/208060142-940052e5-e6f9-4ce5-a8d4-2c52f4235277.png)

![Screenshot 2022-12-16 at 2 19 29 PM](https://user-images.githubusercontent.com/43700789/208060208-59f5a1d0-c50a-4399-bffd-cc4fdbbce006.png)

  This shows how chnages and activity has been reflected and this can be termed as Synthesis simulation mismatch.
  
 - In the similar maner one more example blocking_caveat.v has been implemented, which describes about how blocking statements without synthesis and GLS can show error flops which can churnout the design process. 
  
 ## Follwing is the commands for implemetning these designs 
  
  ``` 
  Code for Synthesis
  yosys  
  read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib  
  read_verilog bad_mux.v  
  synth -top bad_mux  
  abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib  
  show  
  
  Code for  Netlist
  write_verilog -noattr bad_mux_netlist.v
  !gvim bad_mux_netlist.v
  
  Code for GLS 
  iverilog ../my_lib/verilog_model/primitives.v ../my_lib/verilog_model/sky130_fd_sc_hd.v ternary_operator_mux_net.v tb_ternary_operator_mux.v
  ./a.out
  gtkwave tb_ternary_operator_mux.v.
  ```
  
  
  </details>
 
  <details><summary> DAY-5  </summary>  
  
  # Day 5 - If, case, for loop and for generate
  
  > If condition and Inferred latches
    
   If can be defined as the priority logic. It executes statements like a genereal python code. Once the condition is met it executes the function and generates the output without evaluating the other mentioned conditions. This will be an issue in HDL and similarly in complete If statements will trigger Inferred latches. Inferred latches can be defined as a implementation of a latch as it is not explicitly defined as a latch in the code. Instead, it is synthesized from the combination of the if statement and the clock edge event. In this way, the latch is "inferred" from the behavior of the circuit. 
   
   Examaple for the Inferred latch 
   
   ```
   module latch (input wire clk, data,  // Clock and data inputs
              output reg q);         // Output

always @(posedge clk) begin
  if (data) begin
    q <= 1;
  end else begin
    q <= 0;
  end
end

endmodule
```
   
 > Case Constructs
   
   A case construct refers to a type of control flow statement that allows a designer to specify a set of actions to be taken based on the value of a particular input signal or variable. Unlike If conditions, case statements execute the code sequentially and generate the output after the final. These can be considered similar to the switch statement in other programming languages. 
   
   In addtion to this there's an default condition that is used to avoid inferred latches because it ensures that the outputs are always explicitly defined for all possible values of the sel input. If the default case were not included, the synthesizer might infer a latch to hold the previous output value if the sel input does not match any of the other cases. This could result in unintended behavior or undesired timing characteristics in the final circuit.
   
   ```
   module decoder (input [1:0] sel,  // Select input
               output reg a, b, c, d);  // Outputs

always @* begin
  case (sel)
    2'b00: a <= 1; b <= 0; c <= 0; d <= 0;
    2'b01: a <= 0; b <= 1; c <= 0; d <= 0;
    2'b10: a <= 0; b <= 0; c <= 1; d <= 0;
    2'b11: a <= 0; b <= 0; c <= 0; d <= 1;
    default: a <= 0; b <= 0; c <= 0; d <= 0;
  endcase
end

endmodule
 ```
   > Potential Caveats while using the case statements
   
   - Partial assignments - [Note:  Happens when all the outputs are not assigned, so always make sure that all the outputs are assigned] 
   - Overlapping cases -  [ Note: We should not have overlapping case statements as they have potential to generate unpredictable outputs]
   
 > Lab Incomplete IF 
   
  ![Screenshot 2022-12-16 at 4 24 32 PM](https://user-images.githubusercontent.com/43700789/208085190-34496caa-9d00-4edc-90e7-2a1b6185f5cd.png)
   
  ![Screenshot 2022-12-16 at 4 28 12 PM](https://user-images.githubusercontent.com/43700789/208085205-12682632-1e85-4f19-97bb-2c3aad0d6cf7.png)
   
   There's are few more similar examples in the directory that can be implemented. 
 
  >  Lab In-complete Overlapping Case
   
   ![Screenshot 2022-12-16 at 4 49 54 PM](https://user-images.githubusercontent.com/43700789/208088075-0390f9ab-6d51-4199-bd9f-e0b41b0e5aeb.png)

   ![Screenshot 2022-12-16 at 4 50 40 PM](https://user-images.githubusercontent.com/43700789/208088040-268b92d9-e7e9-4c4c-84cd-01ed9eb0582d.png)
   
   ![Screenshot 2022-12-16 at 4 53 05 PM](https://user-images.githubusercontent.com/43700789/208088049-9e7b0fba-619b-4316-8882-0b61e9b117b7.png)

  > Lab Complete case 
    
   - This includes default without a latch. 
   
  ```
   module comp_case (input i0 , input i1 , input i2 , input [1:0] sel, output reg y);
always @ (*)
begin
	case(sel)
		2'b00 : y = i0;
		2'b01 : y = i1;
		default : y = i2;
	endcase
end
endmodule
  ```
   ![Screenshot 2022-12-16 at 5 02 57 PM](https://user-images.githubusercontent.com/43700789/208089624-bc0676e6-ec82-4b7f-bc26-3bbcc9a4d343.png)

   ![Screenshot 2022-12-16 at 5 04 10 PM](https://user-images.githubusercontent.com/43700789/208089642-77e9e4fa-23d1-4d2c-ab2b-1317e08825c5.png)
   
  - Now we will check a partial case where the design is incomplete even after including default. 
   
   ```
   module partial_case_assign (input i0 , input i1 , input i2 , input [1:0] sel, output reg y , output reg x);
always @ (*)
begin
	case(sel)
		2'b00 : begin
			y = i0;
			x = i2;
			end
		2'b01 : y = i1;
		default : begin
		           x = i1;
			   y = i2;
			  end
	endcase
end
endmodule
   ```
   sel[1]+ SEL[0] = EN <sub> Based on redunduncy therom </sub>
   
 ![Screenshot 2022-12-16 at 5 36 39 PM](https://user-images.githubusercontent.com/43700789/208094754-0797ed34-7e69-4286-b40f-4d974429b2a5.png)
   
   We will see a latch in the path of the X.
 ![Screenshot 2022-12-16 at 5 37 10 PM](https://user-images.githubusercontent.com/43700789/208095003-0cb4f1b5-1d5a-40bb-8713-3fc0a13f60ea.png)
   
 - In the similar way we have implemented and worked on bad_case.v file from the directory. Addtionally we did GLS for this so that we can notice how the signals are not overlapping. 
   
![Screenshot 2022-12-16 at 5 51 19 PM](https://user-images.githubusercontent.com/43700789/208097410-feb543bc-ef30-4ffa-b695-95388497c0e8.png)
   
 ## For loop and For generate 
    
    - Looping constructs
   
      - For loop used for evaluating expressions[ Inside always]
      - Generate followed by for loop used for instantiating and replicating hardware [ outside always and cannot be used inside always]
      - Similarly we can implement If generate in the same manner as For generate.
   
   ```
  / Code for Mux using for loop 
  (input [31:0] Bus); 
  integer i;
  always @(*) begin
    for (i = 0; i < 32; i = i + 1) begin
      if (i == sel) 
      y = input[i];
    end
  end. 
   ```
 Building 8 AND gates using For generate 
  ```
  module and_gates(input [7:0] a, input [7:0] b, output [7:0] y);
  genvar i;
  generate
    for (i = 0; i < 8; i = i + 1)
      y[i] = a[i] & b[i];
  endgenerate
endmodule
```
  > Lab For and For generate
   
   ![Screenshot 2022-12-16 at 6 41 41 PM](https://user-images.githubusercontent.com/43700789/208108206-e367ca32-6f1d-4f4b-b24e-169604986eec.png)

 > For genreate RCA   
   
  ![Screenshot 2022-12-16 at 7 20 11 PM](https://user-images.githubusercontent.com/43700789/208112774-61afcd8c-38e9-4207-a0e6-bcc9a002ef27.png)
   
   With synthesis and GLS
   
  ![Screenshot 2022-12-16 at 7 18 54 PM](https://user-images.githubusercontent.com/43700789/208112863-7b735cdb-b9f4-4f16-b091-a8ba43904cdc.png)

        

   
   
      
  
  
  
  
