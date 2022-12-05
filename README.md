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

