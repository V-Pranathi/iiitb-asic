# Physical Design Of ASICs #
## Table of Contents ##
* [Day1](#Day1)
     * Yosys
     * iverilog
     * gtkwave
     * OpenSTA
     * ngspice
     * magic
     * OpenLane
## Day1 ##
<details>
    <summary>
     Yosys     
    </summary>
I installed Yosys using the following commands:    

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

Below is the screenshot showing successfull launch  

![Screenshot from 2023-07-31 09-49-23](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/59e01e06-8888-4941-b74e-a5bfce71934e)
</details>
<details>
    <summary>
    iverilog 
    </summary>

I installed iverilog using the following command:
```
sudo apt-get install iverilog
```
Below is the screenshot showing successful launch:

![Screenshot from 2023-07-31 09-50-01](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/968ce75b-ab04-4fd6-950e-f855497277a9)
</details>
<details>
<summary>
    gtkwave
</summary>
I installed gtkwave using the following command:

```
sudo apt-get install gtkwave
```

Below is the screenshot showing successful launch
![Screenshot from 2023-07-31 09-54-34](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/a87a7a8c-f501-4b35-be79-7526b6daf53f)
![Screenshot from 2023-07-31 09-54-01](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/89be5ae7-f754-4e20-8623-c5e5a810f271)
</details>
<details>
   <summary>
       OpenSTA
   </summary> 
    Installing OpenSTA using the following commands: 
    
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
