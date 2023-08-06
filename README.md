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
<details>
    <summary>
        magic
    </summary>
    Steps to install magic

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
    Steps to install OpenLane:

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

### Check Dependencies ###

    git --version
    docker --version
    python3 --version
    python3 -m pip --version
    make --version
    python3 -m venv -h
![Screenshot from 2023-08-06 12-57-47](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/35b24fcc-68b2-41e7-ad90-123d8e0e89af)
![Screenshot from 2023-08-06 12-58-17](https://github.com/V-Pranathi/iiitb-asic/assets/140998763/f9dce05e-884e-48b0-81ad-0acaca831b3a)

### Steps to Install PDKs and tools ###  

    cd $HOME
    git clone https://github.com/The-OpenROAD-Project/OpenLane
    cd OpenLane
    make
    make test

</details>
