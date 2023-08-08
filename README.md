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
This report is submission of the workshop from VSD-IAT on RTL designing and synthesis using open source tools. The tools used are iVerilog, GTKWave, Yosy and Skywater 130nm Standard Cell Libraries. 
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


## Contributors ##
* Valipireddy Pranathi
* Kunal Ghosh
## Acknowledgement ##
I would like to express my gratitute to VLSI System Design(VSD-IAT) for designing and structuring such a wonderful workshop which gives various insights on the tips and tricks to be followed and noticed while designing a VLSI System. It gave me a lot of perspective on how to think on a hardware level rather than on a software level. A special mention to Kunal Ghosh for helping us out throughout the workshop.
