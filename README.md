# RTL design using Verilog with SKY130 Technology  #
## Table of Contents ##
* [1.Introduction](#1-introduction)
* [2.Tools Installation](#2-tools-installation)
     * [Yosys](#yosys)
     * [iverilog](#iverilog)
     * [gtkwave](#gtkwave)
     * [OpenSTA](#opensta)
     * [ngspice](#ngspice)
     * [magic](#magic)
     * [OpenLane](#openlane)
* [3.Day-1- Introduction to Verilog RTL design and Synthesis](#3-day-1--introduction-to-verilog-rtl-design-and-synthesis)
    * [3.1 SKY130RTL D1SK1 - Introduction to open-source simulator iverilog](#3-1-sky130rtl-dlsk1-introduction-to-open-source-simulator-iverilog)
        * [3.1.1 SKY130RTL D1SK1 L1 Introduction iverilog design and test bench](#3-1-1-sky130rtl-d1sk1-l1-introduction-iverilog-design-and-test-bench)
    * [3.2 SKY130RTL D1SK2 - Labs using iverilog and gtkwave](#3-2-sky130rtl-d1sk2---labs-using-iverilog-and-gtkwave)
        * [3.2.1 SKY130RTL D1SK2 L1 Lab 1 Introduction to Lab](#3-2-1-sky130rtl-d1sk2-l1-lab-1-introduction-to-lab)
        * [3.2.2 SKY130RTL D1SK2 L2 Lab 2 Introduction to iVerilog GTKWave](#3-2-2-sky130rtl-d1sk2-l2-lab-2-introduction-to-iverilog-gtkwave) 
    * [3.3 SKY130RTL D1SK3 - Introduction to Yosys and Logic Synthesis](#3-3-sky130rtl-d1sk3---introduction-to-yosys-and-logic-synthesis)
        * [3.3.1 SKY130RTL D1SK3 L1 Introduction to Yosys](#3-3-1-sky130rtl-d1sk3-l1-introduction-to-yosys)
        * [3.3.2 SKY130RTL D1SK3 L2 Introduction to logic synthesis](#3-3-2-sky130rtl-d1sk3-l2-introduction-to-logic-synthesis) 
    * [3.4 SKY130RTL D1SK4 - Labs Using Yosys and SKY130 PDKs](#3-4-sky130rtl-d1sk4---labs-using-yosys-and-sky130-pdks)
        * [3.4.1 SKY130RTL D1SK4 L1 lab3 Yosys 1 good mux](#3-4-1-sky130rtl-d1sk4-l1-lab3-yosys-1-good-mux)
* [Contributors](#contributors)
* [Acknowledgement](#acknowledgement)
## <a name="1-introduction"></a> 1.Introduction ##  
This report is about the labs we perform from VSD-IAT on RTL designing and synthesis using open source tools. The tools used are iVerilog, GTKWave, Yosy and Skywater 130nm Standard Cell Libraries. 
## <a name="2-tools-installation"></a> 2.Tools Installation ##
<details> 
    <summary>
        Yosys     
    </summary>

#### Steps to install Yosys ####
```
$ git clone https://github.com/YosysHQ/yosys.git  
$ cd yosys-master   
$ sudo apt install make (If make is not installed please install it)   
$ sudo apt-get install build-essential clang bison flex \
    libreadline-dev gawk tcl-dev libffi-dev git \
    graphviz xdot pkg-config python3 libboost-system-dev \
    libboost-python-dev libboost-filesystem-dev zlib1g-dev
$ make config-gcc  
$ make   
$ sudo make install
```
![Screenshot from 2023-07-31 09-49-23](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/59e01e06-8888-4941-b74e-a5bfce71934e)
</details>
<details>
    <summary>
     iverilog 
    </summary>

#### Steps to install iverilog ####
```
sudo apt-get install iverilog
```
![Screenshot from 2023-07-31 09-50-01](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/968ce75b-ab04-4fd6-950e-f855497277a9)
</details>
<details>
    <summary>
     gtkwave
    </summary>

#### Steps to install gtkwave ####

```
sudo apt-get install gtkwave
```
![Screenshot from 2023-07-31 09-54-34](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/a87a7a8c-f501-4b35-be79-7526b6daf53f)
![Screenshot from 2023-07-31 09-54-01](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/89be5ae7-f754-4e20-8623-c5e5a810f271)
</details>
<details>
    <summary>
     OpenSTA
    </summary> 
    
#### Steps to install OpenSTA  ####
    
    # Dependencies for OpenSTA
    sudo apt-get install cmake clang gcc tcl swig bison flex 
    
    # Commands to Install OpenSTA 
    git clone https://github.com/The-OpenROAD-Project/OpenSTA.git
    cd OpenSTA
    mkdir build
    cd build
    cmake ..
    make
    sudo make install  
![Screenshot from 2023-08-06 11-54-21](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/d2b030d7-c192-4d94-a82d-9b30872c91d7)

</details>
<details>
    <summary>
     ngspice
    </summary>

#### Steps to install ngspice ####
After downloading the tarball from https://sourceforge.net/projects/ngspice/files/ to a local directory, unpack it using:  

    # ngspice installation:
    tar -zxvf ngspice-40.tar.gz
    cd ngspice-40
    mkdir release
    cd release
    ../configure  --with-x --with-readline=yes --disable-debug
    make
    sudo make install  
![Screenshot from 2023-08-06 12-17-12](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/5f3dca7a-eca9-49fb-b347-e4e81123e227)

</details>
<details>
    <summary>
     magic
    </summary>
    
#### Steps to install magic ####

    $   sudo apt-get install m4
    $   sudo apt-get install tcsh
    $   sudo apt-get install csh
    $   sudo apt-get install libx11-dev
    $   sudo apt-get install tcl-dev tk-dev
    $   sudo apt-get install libcairo2-dev
    $   sudo apt-get install mesa-common-dev libglu1-mesa-dev
    $   sudo apt-get install libncurses-dev
    git clone https://github.com/RTimothyEdwards/magic
    cd magic
    ./configure
    make
    sudo make install
![Screenshot from 2023-08-06 12-27-39](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/c88600ba-1dc0-4347-a2b1-48e3d673a6a5)
</details>
<details>
    <summary>
     OpenLane
    </summary>
   
#### Steps to install OpenLane ####

    sudo apt-get update
    sudo apt-get upgrade
    sudo apt install -y build-essential python3 python3-venv python3-pip make git
    sudo apt install apt-transport-https ca-certificates curl software-properties-common
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

    echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee     /etc/apt/sources.list.d/docker.list > /dev/null

    sudo apt update
    sudo apt install docker-ce docker-ce-cli containerd.io
    sudo docker run hello-world

    sudo groupadd docker
    sudo usermod -aG docker $USER
    sudo reboot 


    # After reboot
    sudo docker run hello-world
![Screenshot from 2023-08-06 12-54-13](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/0f1dd611-1b0c-4f9e-8920-3eba8a9ca58e)

#### Check Dependencies ####

    git --version
    docker --version
    python3 --version
    python3 -m pip --version
    make --version
    python3 -m venv -h
![Screenshot from 2023-08-06 12-57-47](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/35b24fcc-68b2-41e7-ad90-123d8e0e89af)
![Screenshot from 2023-08-06 12-58-17](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/f9dce05e-884e-48b0-81ad-0acaca831b3a)

#### Steps to Install PDKs and tools ####  

    cd $HOME
    git clone https://github.com/The-OpenROAD-Project/OpenLane
    cd OpenLane
    make
    make test
</details>

## <a name="3-day-1--introduction-to-verilog-rtl-design-and-synthesis"> </a> 3.Day-1- Introduction to Verilog RTL design and Synthesis ##
### <a name="3-1-sky130rtl-dlsk1-introduction-to-open-source-simulator-iverilog"> </a> 3.1 SKY130RTL D1SK1 - Introduction to open-source simulator iverilog ###
#### <a name="3-1-1-sky130rtl-d1sk1-l1-introduction-iverilog-design-and-test-bench"> <a/> 3.1.1 SKY130RTL D1SK1 L1 Introduction iverilog design and test bench ####
**RTL Design:** It is basically the implementation of specifications. RTL design lies between high-level behavioral design and low-level gate-level design. It captures the functionality of the circuit at a level where data transfers between registers are the main focus, while ignoring the specific implementation details of gates and transistors. In general,the RTL designs are described using HDLs like Verilog or VHDL.  
**Test Bench:** Test bench gives stimulus to the design which is under test and verify the functionality of the design we described in verilog. Test bench is written seperately by instantiating the design which need to be simulated. 

![Screenshot from 2023-08-08 19-51-32](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/1e187333-b095-4772-bc5a-b96f3227d82f)

**Simulator:**  It is a tool used to check if it adheres to the designed specifications by simualating the code. It looks for changes on input signals to evaluate outputs. There will be no change in output if there is no change in input signals.

### <a name="3-2-sky130rtl-d1sk2---labs-using-iverilog-and-gtkwave"> </a> 3.2 SKY130RTL D1SK2 - Labs using iverilog and gtkwave ###
**iverilog:** IVERILOG is an open-source Verilog simulation and synthesis tool that is commonly used for designing and verifying digital circuits described in the Verilog hardware description language (HDL).  
**GTKwave:** GTKWave is a popular open-source waveform viewer that allows to visualize and analyze digital signal waveforms generated during simulations of digital circuits. It is often used in conjunction with simulation tools like IVERILOG to provide a graphical representation of how signals change over time in a digital design.  

![Screenshot from 2023-08-08 20-02-40](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/550de8bd-55d2-4da1-910d-03020ebe5930)

#### <a name="3-2-1-sky130rtl-d1sk2-l1-lab-1-introduction-to-lab"> </a> 3.2.1 SKY130RTL D1SK2 L1 Lab 1 Introduction to Lab ####
In this we created an environment setup for running the labs.  
To set up the tool flow we used the commands below:  

    $ git clone https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git
    $ cd sky130RTLDesignAndSynthesisWorkshop

![Screenshot from 2023-08-08 21-56-06](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/567dd875-6b43-40e8-aaa7-511fb6cf6381)

The verilog files used in this workshop:

![Screenshot from 2023-08-08 22-01-49](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/04876a23-c40e-4ffe-b149-853501cc39fa)

#### <a name="3-2-2-sky130rtl-d1sk2-l2-lab-2-introduction-to-iverilog-gtkwave"> </a> 3.2.2 SKY130RTL D1SK2 L2 Lab 2 Introduction to iVerilog GTKWave ####
From the verilog files as seen above I selected multiplexer design. Load both the RTL design code and its associated test bench code in iverilog to generate vcd file which is used in gtkwave generator to get the output waveformes after simulation. The output was generated by taking the inputs from the testbench code. The following snippet is the verilog code and its testbench.

    //mux
    module good_mux (input i0 , input i1 , input sel , output reg y);
    always @ (*)
    begin
     if(sel)
            y <= i1;
     else
            y <= i0;
    end
    endmodule

    //testbench
    `timescale 1ns / 1ps
        module tb_good_mux;
        // Inputs
        reg i0,i1,sel;
        // Outputs
        wire y;

        // Instantiate the Unit Under Test (UUT)
        good_mux uut (
                .sel(sel),
                .i0(i0),
                .i1(i1),
                .y(y)
        );

        initial begin
        $dumpfile("tb_good_mux.vcd");
        $dumpvars(0,tb_good_mux);
        // Initialize Inputs
        sel = 0;
        i0 = 0;
        i1 = 0;
        #300 $finish;
        end

        always #75 sel = ~sel;
        always #10 i0 = ~i0;
        always #55 i1 = ~i1;
        endmodule
The commands to simulate the design is as follows:

![Screenshot from 2023-08-08 22-13-29](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/2c1d1ee2-5b19-4c60-971a-f055ab9c2703)

GTK wave generates the output waveforms after simulation and is as follows:

![Screenshot from 2023-08-08 22-14-08](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/59f657ea-ff58-440e-9676-0b90019d099c)

### <a name="3-3-sky130rtl-d1sk3---introduction-to-yosys-and-logic-synthesis"> </a> 3.3 SKY130RTL D1SK3 - Introduction to Yosys and Logic Synthesis ###
**Synthesis:** Synthesis is nothing but conversion of RTL design which is writeen in verilog or any other HDL into the netlist which gives the interconnection of components.The netlist is then supposed to perform the same function as the corresponding HDL code. Synthesizer is the tool which convert RTL design into the netlist form. One of such tool is Yosys.
#### <a name="3-3-1-sky130rtl-d1sk3-l1-introduction-to-yosys"> </a> 3.3.1 SKY130RTL D1SK3 L1 Introduction to Yosys ####
**Yosys:** Yosys aims to converting high-level hardware descriptions into optimized gate-level representations that can be targeted for various FPGA and ASIC technologies. The flow for yosys is we feed the yosys with the design which is in RTL level and the .lib file which contain standard library cells then the yosys synthesizes and gives us the netlist file.
The commands to perform synthesis are:

_RTL Design - read_verilog_  
_.lib - read_liberty_  
_netlist file- write_verilog_  

**The flow of Yosys Synthesis**

![Screenshot from 2023-08-08 22-40-51](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/5d6b1a6b-9233-41db-821d-f5c103ab63e1)

The netlist is the representation of the design in the form of standard library cells. 
**Verification of Synthesis**
After the synthesis we need to check whether the netlist we got is valid or not and that can be done by matching the waveforms before and after synthesis. The same testbench that is used for the simulation can be used for the synthesized netlist as well. 

![Screenshot from 2023-08-08 22-56-49](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/5af55b95-0c51-4d5b-87cc-117c284a0759)

#### <a name="3-3-2-sky130rtl-d1sk3-l2-introduction-to-logic-synthesis"> </a> 3.3.2 SKY130RTL D1SK3 L2 Introduction to logic synthesis  ####
* RTL to gate level translation
* The RTL design is converted into gates and the connections are made between gates.
* This is given out as a file called netlist. 
<p align="center">
<img src=https://github.com/V-Pranathi/iiitb-asic/assets/140998763/19e70b7b-e195-41bb-ae1c-43f39edcf5bd> <br>
</p>

**.lib:**
 * Collection of logic modules.
 * It contains all different kind of logic modules. like AND, OR, NOR etc.
 * It contains different variants of the same gate as well. like 2input, 3input, 4input, slow, fast, medium gates etc.
   
**Why different flavours of gates?** Let us consider a circuit as shown below. So in this circuit for the clock frequency to be maximum so as to make a faster circuit the time period of the clock should be minimum. However, Clock period depends on propagation delay of flipflop A, propogation delay of Combinational circuit and the setup time of the flipflop B.
<p align="center">
<img src=https://github.com/V-Pranathi/iiitb-asic/assets/140998763/2c9423ee-fea5-4ba2-9089-6254a9bf5b79> <br>
</p>

So we need cells that work fast to make combinational delay small. So now why do we need slower cells? To ensure that ther eare no hold issues at fliflop B, we need cells that work slowly.This complete collection forms .lib.  

**Faster cells vs Slower cells**
 * Load in a digital logic circuit is a capacitor.
 * Fater the charging and discharging of capacitance the lesser is the delay.
 * To charge/Discharge the capacitor fast, we need transistors capable of sourcing more current.
 * Wider transistors -> low delay -> More Power and Area.
 * Narrow transitor -> More delay -> Less Area and Power.
   
**Selection of cells** 
 * Need to guide the synthesizer to select the flavour of cells that is optimum for the implementation of logic circuits.
 * More use of fast cells can be bad interms of power and area.
 * More use of slow cells can lead to a sluggish circuit.
 * The guidence offered to the synthesizer is called _constraints_.

Below is the Synthesis illustration:

![Screenshot from 2023-08-08 23-34-46](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/6775c62a-17d6-4c42-b9bc-453cc25cf381)

### <a name="3-4-sky130rtl-d1sk4---labs-using-yosys-and-sky130-pdks"> </a> 3.4 SKY130RTL D1SK4 - Labs Using Yosys and SKY130 PDKs ###
#### <a name="3-4-1-sky130rtl-d1sk4-l1-lab3-yosys-1-good-mux"> </a> 3.4.1 SKY130RTL D1SK4 L1 lab3 Yosys 1 good mux ####
Invoking Yosys:

![Screenshot from 2023-08-08 23-40-16](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/cad80801-05af-4607-9254-40a16759a458)

Commands for synthesis:

    $ yosys
    $ read_liberty -lib /home/nandu/ASIC/sky130RTLDesignAndSynthesisWorkshop/lib/sky130_fd_sc_hd__tt_025C_1v80.lib
    $ read_verilog good_mux.v
    $ synth -top good_mux
    $ abc -liberty /home/nandu/ASIC/sky130RTLDesignAndSynthesisWorkshop/lib/sky130_fd_sc_hd__tt_025C_1v80.lib
    $ show
    $ write_verlog good_mux_netlist.v
    $ write_verilog -noattr good_mux_netlist.v

Reading the design,.lib files and the module to synthesize

![Screenshot from 2023-08-08 23-48-59](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/bec0b6c4-eb82-4175-a429-ebf0beb76730)

![Screenshot from 2023-08-08 23-49-20](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/46fb6ed0-82ba-4e14-a487-dae97b4e0582)

Writing the verilog file and generating the netlist

![Screenshot from 2023-08-08 23-56-11](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/18c6d04e-41ca-4b2a-9606-79fef1edf8bb)

![Screenshot from 2023-08-08 23-56-25](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/96cd3a8d-8e08-4df4-b079-a7d8d60d0d69)

Synthesized circuit

![Screenshot from 2023-08-08 23-58-59](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/7091da03-445f-4640-ab5a-5a47874f2cd2)

Netlist file

![Screenshot from 2023-08-09 00-10-41](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/ed461304-20aa-4934-8c0b-3b8e9c9ffb97)

![Screenshot from 2023-08-09 00-09-30](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/5615a60c-83c7-407c-949a-f3f21a1c8bee)

Modify the switch to get the simplified netlist code

![Screenshot from 2023-08-09 00-15-27](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/0da361de-a088-4b94-89a8-51a6f93c888b)


![Screenshot from 2023-08-09 00-15-10](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/e3eff44e-fa1f-40c6-a5ed-110124a330cf)
## <a name="4-day-2--timing libs--hierarchical-vs-flat-synthesis-and-efficient-flop-coding-styles"> </a> 4.Day-2- Timing libs, hierarchical vs flat synthesis and efficient flop coding styles ##
### <a name="4-1-sky130rtl-d2sk1---introduction-to-timing--libs"> </a> 4.1 SKY130RTL D2SK1 - Introduction to timing .libs ###
As we already know .lib is a collection of standard cells. Now we will see what actually .lib file contains.  

![Screenshot from 2023-08-13 14-54-30](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/cf3a1d1f-1bd1-4e42-b376-d7a7452d7ac8)  

In the above screenshot we can see that there is this "sky130_fd_sc_hd__tt_025C_1v80". Actually there is some significance for that.  

_**130** 130nm library_  
_**tt** signifies the process which is typical_  
_**025C** signifies the temperature_  
_**1v80** signifies the voltage_  

The variations in PVT(Proces,Voltage and Temperature) determines how the semiconductor behaves.  
The default operating conditions are as shown below 

![Screenshot from 2023-08-13 15-24-31](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/9fa854ff-7ecd-466b-ba59-38589c3f296e)  

We will see the different flavours the same cell for and gate

![Screenshot from 2023-08-13 15-40-32](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/58b2259f-2ccf-409d-8bda-bdb0a18d7ff7)
![Screenshot from 2023-08-13 15-40-53](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/c63514a8-e7c7-4e29-8933-0dd82d569fc7)
![Screenshot from 2023-08-13 15-41-38](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/9be2c8a9-b04a-42a5-830e-a76c2b87df0d)

What it is showing?  
* and2_0 -- taking the least area, more delay and low power.  
* and2_1 -- taking more area, less delay and high power.
* and2_2 -- taking the largest area, larger delay and highest power.
### <a name="4-2-sky130rtl-d2sk2---hierarchical-vs-flat-synthesis"> </a> 4.2 SKY130RTL D2SK2 - Hierarchical vs Flat Synthesis ### 
We can explain hierarchial and flat synthesis using an example module(which has two submodules) given below:  
    
    module sub_module2 (input a, input b, output y);
        assign y = a | b;
    endmodule

    module sub_module1 (input a, input b, output y);
        assign y = a&b;
    endmodule


    module multiple_modules (input a, input b, input c , output y);
        wire net1;
        sub_module1 u1(.a(a),.b(b),.y(net1));  //net1 = a&b
        sub_module2 u2(.a(net1),.b(c),.y(y));  //y = net1|c ,ie y = a&b + c;
    endmodule

**Hierarchial synthesis:** In the hierarchial synthesis the hierarchies are preserved. We can see the sub_module1(u1) and sub_module2 (u2) as above. The hierarchial netlist code is given below.

    module multiple_modules(a, b, c, y);
          input a;
          wire a;
          input b;
          wire b;
          input c;
          wire c;
          wire net1;
          output y;
          wire y;
      sub_module1 u1 (
            .a(a),
            .b(b),
            .y(net1)
              );
      sub_module2 u2 (
            .a(net1),
            .b(c),
            .y(y)
              );
    endmodule

    module sub_module1(a, b, y);
          wire _0_;
          wire _1_;
          wire _2_;
          input a;
          wire a;
          input b;
          wire b;
          output y;
          wire y;
      sky130_fd_sc_hd__and2_0 _3_ (
                .A(_1_),
                .B(_0_),
                .X(_2_)
              );
      assign _1_ = b;
      assign _0_ = a;
      assign y = _2_;
    endmodule

    module sub_module2(a, b, y);
              wire _0_;
              wire _1_;
              wire _2_;
              input a;
              wire a;
              input b;
              wire b;
              output y;
              wire y;
      sky130_fd_sc_hd__or2_0 _3_ (
                .A(_1_),
                .B(_0_),
                .X(_2_)
                  );
      assign _1_ = b;
      assign _0_ = a;
      assign y = _2_;
    endmodule
    
![Screenshot from 2023-08-13 22-00-27](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/307df294-99fe-43c6-a8a8-fa62226d2287)

**Flat synthesis:** In the flat synthesis hierarchies are flattened out and directly instantiates gates here. The flattened netlist is given below.

    module multiple_modules(a, b, c, y);
          wire _0_;
          wire _1_;
          wire _2_;
          wire _3_;
          wire _4_;
          wire _5_;
          input a;
          wire a;
          input b;
          wire b;
          input c;
          wire c;
          wire net1;
          wire \u1.a ;
          wire \u1.b ;
          wire \u1.y ;
          wire \u2.a ;
          wire \u2.b ;
          wire \u2.y ;
          output y;
          wire y;
      sky130_fd_sc_hd__and2_0 _6_ (
                .A(_1_),
                .B(_0_),
                .X(_2_)
                  );
      sky130_fd_sc_hd__or2_0 _7_ (
                .A(_4_),
                .B(_3_),
                .X(_5_)
                  );
      assign _4_ = \u2.b ;
      assign _3_ = \u2.a ;
      assign \u2.y  = _5_;
      assign \u2.a  = net1;
      assign \u2.b  = c;
      assign y = \u2.y ;
      assign _1_ = \u1.b ;
      assign _0_ = \u1.a ;
      assign \u1.y  = _2_;
      assign \u1.a  = a;
      assign \u1.b  = b;
      assign net1 = \u1.y ;
    endmodule

![Screenshot from 2023-08-13 21-58-17](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/19ab9080-0dd4-4de3-8576-2e46f109bc5f)  

The commands for hierarchial and flat synthesis are:

    $ yosys
    yosys> read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
    yosys> read_verilog multiple_modules.v
    yosys> synth -top multiple_modules
    yosys> abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

    //hierarchial synthesis
    yosys> show multiple_modules
    yosys> write_verilog -noattr multiple_modules_hier.v
    yosys> !vim multiple_modules_hier.v

    //flat synthesis
    yosys> flatten
    yosys> write_verilog -noattr multiple_modules_flat.v
    yosys> !vim multiple_modules_flat.v

The example verilog file multiple_modules has two sub modules and those can be synthesized at sub module level.. We control the module which we are synthesizing using the keyworf _**"synth -top <module_name>"**_.  
**Why we need sub module level synthesis?**  
* Sub module level synthesis is preferred when we have multiple instances of same module. If the same module is getting instantiated multiple times instead of synthesizing the same module multiple times we can synthesize it once and replicate the corresponding netlist multiple times and stitch together to get the top module netlist.
* Divide and Conquer approach. If the design is very massive the tools might not do a good job. So what we do is we synthesize parts by parts which gives us optimized netlists and all netlists can be stitched to get the top module netlist.
  
![Screenshot from 2023-08-13 22-33-58](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/e6c393c6-8f02-46ca-807b-6edb984910b7)

### <a name="4-3-sky130rtl-d2sk2---various-flop-coding-styles-and-optimization"> </a> 4.3 SKY130RTL D2SK2 - Various Flop Coding Styles and Optimization ###  
#### <a name="4-3-1-sky130rtl-d2sk2---why-flops-and-flop-coding-styles"> </a> 4.3.1 SKY130RTL D2SK2 - Why Flops and Flop coding styles ####  
**Why a Flop?**  
In a combinational circuit to get the corresponding output for the given inputs, there will be a propagation delay. But during that delay we will get intermediate outputs due to different paths in that combinational circuit which are actually called glitches. The more combinational circuits we have the more glitchy the output will be making the output unstable.  

So, to avoid the glitches we need an element to store the value. That element is called a flop. By using a flop we are storing the output of the combinational circuit so as it will become the input to the next combinational only when the posedge or negedge of the clock is applied making the input stable to the combinational circuit thereby curbing the glitches.

We need to initialize the flop otherwise the succeding combinational circuit takes garbage value as input. So we have control pins **reset** and **set**. 

**Flop coding styles**
* Asynchronous reset
* Synchronous reset
* Asynchronous set
* Synchronous set
* Both Asynchronous reset and Synchronous reset
* Both Asynchronous set and Synchronous set
#### <a name="4-3-2-sky130rtl-d2sk2---lab-flop-synthesis-simulation"> </a> 4.3.2 SKY130RTL D2SK2 - lab Flop Synthesis Simulation ####  
**D-flipflop with Asynchronous reset --** Whenever the reset is high the output goes low irrespective of the clock is changed or not. The below figure clealry explains the asynchronous reset mode.

![WhatsApp Image 2023-08-13 at 23 28 28](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/785c013c-34ef-4842-80fb-4da232e370eb)

The verilog code for D-flipflop with asynchronous reset is

     module dff_asyncres ( input clk ,  input async_reset , input d , output reg q );
	always @ (posedge clk , posedge async_reset)
	begin
		if(async_reset)
			q <= 1'b0;
		else	
			q <= d;
	end
    endmodule

**Simulation:**

![Screenshot from 2023-08-13 23-45-12](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/12c1cb9d-8df7-4904-8518-a8be69d7b0b0)

**Synthesized circuit**

![Screenshot from 2023-08-14 00-15-44](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/cc2aa36b-7f0d-49f9-b41f-e47aa6f7cdd5)

**D-flipflop with Synchronous reset --** The output changes only when the clock changes i.e., depends on the clock.
The below figure clearly explains the synchronous reset mode.  

![WhatsApp Image 2023-08-13 at 23 28 27(1)](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/ab533151-ffcd-475f-912f-1ff6b0f7c342)

THe verilog code synchronous reset is:

    module dff_syncres ( input clk , input async_reset , input sync_reset , input d , output reg q );
	always @ (posedge clk )
	begin
		if (sync_reset)
			q <= 1'b0;
		else	
			q <= d;
	end
    endmodule



**Simulation**

![Screenshot from 2023-08-13 23-49-49](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/56d459ac-ddac-4a8e-a7f2-794c19b446f8)

**Synthesized circuit**

![Screenshot from 2023-08-14 00-14-22](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/bf123728-02db-4efa-8943-4b0830552867)  


**D-flipflop with Synchronous/Asynchronous reset --**

![WhatsApp Image 2023-08-13 at 23 28 27](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/5a2c0c51-53d5-455c-a4d1-0ebc2fa65e65)

The verilog code for D-flipflop with asynchronous/synchronous reset is

	module dff_asyncres_syncres ( input clk , input async_reset , input sync_reset , input d , output reg q );
	always @ (posedge clk , posedge async_reset)
	begin
        if(async_reset)
                q <= 1'b0;
        else if (sync_reset)
                q <= 1'b0;
        else
                q <= d;
	end
	endmodule
 
 **Simulation**
 
![Screenshot from 2023-08-14 00-37-42](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/34a2ce00-ee75-4668-a707-55b99fbcdd27)  

**Synthesis**

![Screenshot from 2023-08-14 00-42-25](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/778b8617-610d-425e-94b2-4fe4b260b485)

#### <a name="4-3-3-sky130rtl-d2sk3---interesting-optimisations"> </a> 4.3.2 SKY130RTL D2SK3 - Interesting Optimisations ####  

When we perform synthesis yosys optimise the circuit based on the logic. We will see one such optimisation. 

_EXAMPLE1:_ In the below example we can see the multiplication of a number by 2 doesnt really need any extra hardware we just need to append the LSB's with zeroes and the remaining bits are the input bits of same,that is realized by grouding the LSB's and wiring the input properly to the output. Similary, for any number multiply with multiples of 2 we just need to append lsb's with zeroes.

	module mul2 (input [2:0] a, output [3:0] y);
	assign y = a * 2;
	endmodule

Illustration of a number multiply by 2:

![WhatsApp Image 2023-08-14 at 00 34 38](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/4f509da2-4181-43bf-a73b-e770dd4cf8a1)  

**Synthesized circuit and Netlist**

![Screenshot from 2023-08-14 00-47-45](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/edb0d405-ea2c-4c4b-bc79-e398fa6a2c8f)
![Screenshot from 2023-08-14 00-59-33](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/c4010592-e43f-44fc-b9d6-d40866e67e53)

_EXAMPLE2_ 

	module mult8 (input [2:0] a , output [5:0] y);
		assign y = a * 9;
	endmodule

 For the above example we dont need any hardware to implement it.
 
 ![WhatsApp Image 2023-08-14 at 01 11 08](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/f7571e12-934a-457b-8aea-795b61b057f5)

**Synthesized circuit and Netlist**

![Screenshot from 2023-08-14 01-14-47](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/d21b819b-2870-4390-9633-3e553b22e95b)
![Screenshot from 2023-08-14 01-15-30](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/27e5cee1-d5fc-4f3e-b03c-a67d974176a1)

## <a name="5-day-3--combinational-and-sequential-optimizations"> </a> 5.Day-3- Combinational and Sequential Optimizations##
### <a name="5-1-sky130rtl-d2sk1---combinational-logic-optimizations"> </a> 5.1 SKY130RTL D2SK1 - Combinational Logic Optimizations ###
--> The optimisation techniques are done by the synthesis tool yosys using various techniques giving us the optimised circuit.
--> Squeezing the logic to get the most optimised design
   * Area and Power savings  
_Techniques for Optimisation_  
--> Constant Propogation
   * Direct Optimisation
--> Boolean logic optimisation
   * K-Map
   * Quine Mcklusky      
**Constant Propogtion**

![Screenshot from 2023-08-14 01-57-09](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/3133481e-9dd1-40b9-b152-51d2ddb229bc)
![WhatsApp Image 2023-08-14 at 02 07 12](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/7f524025-92b1-4460-99f2-da98f47b1414)
In the above example, based on the boolean expression we will have 6mos transistors to get the output Y. But when we make A zero i.e., making it constant we get the output just by using 2mos transistors since the logic becomes invertor. 
**Boolean Logic Optimisation**
Lets have an expression **assign y=a?(b?c:(c?a:0)):(!c)**. This expression is using ternary operator which can be realized using MUX's. Writing the boolean expression from the mux and then simplfying using boolean reduction techniques the output Y can be reduced to Y = ~(a^c).  
**Note**
For optimiszing the circuit the command to be given in yosys is

	yosys> opt_clean -purge
 
**Example1:**
![WhatsApp Image 2023-08-14 at 03 34 25](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/025c523c-746e-429f-a3c9-33fbb3066ac3)

	module opt_check (input a , input b , output y);
		assign y = a?b:0;
	endmodule
**Optimized Circuit and netlist**
![Screenshot from 2023-08-14 03-40-23](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/8f748961-86a1-4dab-a0ec-218777822286)
![Screenshot from 2023-08-14 03-43-26](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/986b627f-95a5-417b-98e3-2ed1283ba133)

**Example2:**
![WhatsApp Image 2023-08-14 at 03 34 24(1)](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/3c3e1485-c87e-4917-8b27-c22dd8af12e8)

	module opt_check2 (input a , input b , output y);
		assign y = a?1:b;
	endmodule
**Optimized Circuit and netlist** 
![Screenshot from 2023-08-14 03-46-43](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/5b349a3b-8ae0-46b8-9cb6-0ac238dca9ac)
![Screenshot from 2023-08-14 03-47-09](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/360f5a18-fda1-4279-bef8-1554f32677df)

**Example3:**
![WhatsApp Image 2023-08-14 at 03 34 24(2)](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/c94ee5f0-6223-4b02-ab8d-a2c83ead4702)

 	module opt_check3 (input a , input b, input c , output y);
		assign y = a?(c?b:0):0;
	endmodule
**Optimized Circuit and netlist** 
![Screenshot from 2023-08-14 03-48-08](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/c19114a2-dae4-428b-9f14-049732bd22e5)
![Screenshot from 2023-08-14 03-48-32](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/9b0fce98-dd94-4fe2-9efc-310a246c62c1)

**Example4:**

![WhatsApp Image 2023-08-14 at 04 30 55](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/32d5bef5-f59f-4af5-8098-fd2bf01de43a)

	module opt_check4 (input a , input b , input c , output y);
		assign y = a?(b?(a & c ):c):(!c);
	endmodule
**Optimized Circuit and netlist** 
![Screenshot from 2023-08-14 03-55-18](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/d58a4f94-0e72-4c32-bf1f-eab630fc7ce2)
![Screenshot from 2023-08-14 03-55-45](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/19ae5714-3ad5-4d9f-ad64-dd67b5f217cc)

**Example5:**

![WhatsApp Image 2023-08-14 at 04 29 59](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/3941a8fd-045c-446c-a55b-385f968ee793)

	module sub_module(input a , input b , output y);
		assign y = a & b;
	endmodule

	module multiple_module_opt2(input a , input b , input c , input d , output y);
			wire n1,n2,n3;
		sub_module U1 (.a(a) , .b(1'b0) , .y(n1));
		sub_module U2 (.a(b), .b(c) , .y(n2));
		sub_module U3 (.a(n2), .b(d) , .y(n3));
		sub_module U4 (.a(n3), .b(n1) , .y(y));
	endmodule
**Optimized Circuit and netlist**  
![Screenshot from 2023-08-14 04-10-31](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/b0d07142-212a-45be-9f6d-b2c00bfd3c4d)
![Screenshot from 2023-08-14 04-12-02](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/bdce7913-9df7-4d76-be8e-194bc1db41c3)

**Example6:**

![WhatsApp Image 2023-08-14 at 04 30 00](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/5b66f682-c923-464d-bda3-5f1197009f4a)

	module sub_module1(input a , input b , output y);
	 assign y = a & b;
	endmodule

	module sub_module2(input a , input b , output y);
	 assign y = a^b;
	endmodule

	module multiple_module_opt(input a , input b , input c , input d , output y);
	wire n1,n2,n3;
	sub_module1 U1 (.a(a) , .b(1'b1) , .y(n1));
	sub_module2 U2 (.a(n1), .b(1'b0) , .y(n2));
	sub_module2 U3 (.a(b), .b(d) , .y(n3));

	assign y = c | (b & n1); 
	endmodule
**Optimized Circuit and netlist** 
![Screenshot from 2023-08-14 04-14-58](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/f4f232f8-7cc7-43ea-890a-8c3885db4a36)
![Screenshot from 2023-08-14 04-15-30](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/e78b9dcb-59cd-42a0-935f-7f0eda683966)

### <a name="5-2-sky130rtl-d2sk1---sequential-logic-optimizations"> </a> 5.1 SKY130RTL D2SK1 - Sequential Logic Optimizations ###  
--> Basic - Sequential Constant Optimisation  
--> Advanced  
     	* State optimisation  
     	* Retiming  
     	* Sequential Logic Cloning (Floor Plan Aware Synthesis)  
      
**EXAMPLE1**
Here flop will be inferred as the output is not constant

	module dff_const1(input clk, input reset, output reg q);
	always @(posedge clk, posedge reset)
	begin
		if(reset)
			q <= 1'b0;
		else
			q <= 1'b1;
	end
	endmodule
**Synthesis**
![Screenshot from 2023-08-14 05-27-40](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/f1a0e913-de99-4439-a2d7-d1992a2dd406)
![Screenshot from 2023-08-14 05-30-41](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/c3aca558-c4a3-42c8-9afd-5beda3391130)

**EXAMPLE2**
Here flop will not be inferred as the output is constant

	module dff_const2(input clk, input reset, output reg q);
	always @(posedge clk, posedge reset)
	begin
		if(reset)
			q <= 1'b1;
		else
			q <= 1'b1;
	end
	endmodule
**Synthesis**
![Screenshot from 2023-08-14 05-33-01](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/e2dc6b62-1038-4ec3-9305-12ae59a76aef)
![Screenshot from 2023-08-14 05-31-55](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/493bfc56-3446-4292-a9c6-9df194e4dbb6)

**EXAMPLE3**

 	module dff_const3(input clk, input reset, output reg q);
	reg q1;

	always @(posedge clk, posedge reset)
	begin
		if(reset)
		begin
			q <= 1'b1;
			q1 <= 1'b0;
		end
		else
		begin
			q1 <= 1'b1;
			q <= q1;
		end
	end
	endmodule
**Synthesis**
![Screenshot from 2023-08-14 05-41-38](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/7e283c11-a280-4561-98d4-19c1ab5b3433)
![Screenshot from 2023-08-14 05-35-51](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/9e773e02-9020-466b-841f-4c719f8bc064)

**EXAMPLE4**

 	module dff_const4(input clk, input reset, output reg q);
	reg q1;

	always @(posedge clk, posedge reset)
	begin
		if(reset)
		begin
			q <= 1'b1;
			q1 <= 1'b1;
		end
	else
		begin
			q1 <= 1'b1;
			q <= q1;
		end
	end
	endmodule
 **Synthesis**
![Screenshot from 2023-08-14 05-48-39](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/1f309834-4ff8-4ff4-8406-3cfbd1b76d36)
![Screenshot from 2023-08-14 05-47-36](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/40210d3e-ec2a-46e2-9461-0cd5d7134cc1)
 
**EXAMPLE5**

		module dff_const5(input clk, input reset, output reg q);
	reg q1;
	always @(posedge clk, posedge reset)
		begin
			if(reset)
			begin
				q <= 1'b0;
				q1 <= 1'b0;
			end
		else
			begin
				q1 <= 1'b1;
				q <= q1;
			end
		end
	endmodule
 **Synthesis**
![Screenshot from 2023-08-14 05-52-28](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/8ededd10-d4ee-4b25-8289-4e6f04de1def)
![Screenshot from 2023-08-14 05-52-52](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/f758cc65-f936-409f-810d-a0601e4986a5)

**Advanced**

**State Optimisation:** This is optimisation of unused state. Using this technique we can come up with most optimised state machine.

**Cloning:** This is done when performing PHYSICAL AWARE SYNTHESIS. Lets consider a flop A which is connected to flop B and flop C through a combination logic. If B and C are placed far from A in the flooerplan, there is a routing path delay. To avoid this, we connect A to two intermediate flops and then from these flops the output is sent to B and C thereby decreasing the delay. This process is called cloning since we are generating two new flops with same functionality as A.

**Retiming:** Retiming is a powerful sequential optimization technique used to move registers across the combinational logic or to optimize the number of registers to improve performance via power-delay trade-off, without changing the input-output behavior of the circuit.

### <a name="5-3-sky130rtl-d4sk3---sequential-logic-optimizations-for-unused-outputs"> </a> 5.1 SKY130RTL D4SK3 - Sequential Logic Optimizations for unused outputs ###  




## Contributors ##

## Acknowledgement ##

