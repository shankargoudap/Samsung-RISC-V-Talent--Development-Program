# Samsung-RISC-V-Talent--Development-Program
##  Basic Details

**Name:** SHANKARGOUDA PATIL  
**College:** KLE Institue of Technology  
**Email ID:** shankargouda23patil@gmail.com  
**GitHub Profile:** [shankargouda_patil_Github](https://github.com/shankargoudap/Samsung-RISC-V-Talent--Development-Program)  

----------------------------------------------------------------------------------------------------------------

<details>
<summary><b>Task 1:</b>Task is to install all the essential tools required for this samsung-RISCV  Workshop such as Ubuntu on VMBox & refer to C based and RISCV based lab videos and execute the task of compiling the C code using gcc and riscv compiler</summary><br>

### Install Ubuntu 20.04 LTS on Oracle Virtual Machine Box

Firstly, I have downloaded the virtual box from the links provided to us and
loaded a linux version with image dock file sent  
![Ubuntu and VMBox Installation](https://github.com/shankargoudap/Samsung-RISC-V-Talent--Development-Program/blob/main/task1/virtual_machine_installed.png)

### C Language based LAB
I have successfully run the virtual machine and compiled the tasks.

Initial task is:-

### write a program to compile the sum of first 5 natural numbers in c:

we have written the code sum of 1st 5 numbers in leafpad as shown below.

```
gcc sum_1ton.c

./a.out
```

this code will be run in terminal to get output as 15 for 1st 5 numbers as shown below :


![image](https://github.com/shankargoudap/Samsung-RISC-V-Talent--Development-Program/blob/main/task1/C%20Code%20compiled%20on%20gcc%20Compiler.png)

### RISCV based LAB

1. Using the cat command, the entire C code will be displayed on the terminal.
   
![image](https://github.com/shankargoudap/Samsung-RISC-V-Talent--Development-Program/blob/main/task1/cat%20Command.png)

2. A program is run to obtain risc-v version of the code previously written in c:

  	 ```
	riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum_1ton.o sum_1ton.c
	```

![image](https://github.com/shankargoudap/Samsung-RISC-V-Talent--Development-Program/blob/main/task1/RISCV_C_CODE_O1.png)


3. As the whole version of above code looks lengthier we have used below code to make it shorter
	
 	```
	riscv64 -unknown-elf-objdump -d sum1ton.o | less
	```
 
& we have obtained the required main part to compare the execution in assembly language as shown below :

	
 
![image](https://github.com/shankargoudap/Samsung-RISC-V-Talent--Development-Program/blob/main/task1/Objdump%20using%20-O1%20format.png)

4. Open the same terminal and run the given command:
 
 	```
	riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o sum_1ton.o sum_1ton.c
	``` 


![image](https://github.com/shankargoudap/Samsung-RISC-V-Talent--Development-Program/blob/main/task1/RISCV_CODE_Ofast.png)

5. As the whole version of above code looks lengthier as earlier we have used below code to make it shorter
	
 	```
	riscv64 -unknown-elf-objdump -d sum1ton.o | less
	```
 
& we have obtained the required main part to compare the execution in assembly language as shown below :



![image](https://github.com/shankargoudap/Samsung-RISC-V-Talent--Development-Program/blob/main/task1/Objdump%20using%20-Ofast%20format.png)

### End of 1st task
</details>

------------------------------------------------------------------------------------------------------------------

<details>
<summary><b>Task 2:</b> Performing SPIKE Simulation and Debugging the C code with Interactive Debugging Mode using Spike.
	
I understood the principle and working of the whole program and how various registers like stack pointer and r5 are increasing & understood how the interface explains the process itself.
</summary> 

### What is SPIKE in RISCV?
* Spike is a free, open-source C++ simulator for the RISC-V ISA that models a RISC-V core and cache system. It can be used to run programs and a Linux kernel, and can be a starting point for running software on a RISC-V target.

### Testing the SPIKE Simulator for sum1ton.c
**spike_O1_objdump**

* Here we are compare both of the compiler that must display the same output on the terminal.
* after that we are gona debug the sum1ton.c of **-O1_format** using SPIKE simulator

![image](https://github.com/shankargoudap/Samsung-RISC-V-Talent--Development-Program/blob/main/task2/spike_O1_objdump_for_sum1ton.png)

* In the above picture registor a0 earlier has value 21000 in hex decimal.
* After running the registor a0 became 21180 in hexa decimal.
* * Because there has +384 in decimal,so after calculation it gives the above value 

**Spike_Ofast_objdump**

* Here also goes the same we compare both of the compiler that must display the same output on the terminal.
* after that we are gona debug the sum1ton.c of **-Ofast_format** using SPIKE simulator



![image](https://github.com/shankargoudap/Samsung-RISC-V-Talent--Development-Program/blob/main/task2/spike_Ofast_objdump_for_sum1ton.png)

* In the above picture registor sp earlier has value 3ffffffb50 in hex decimal.
* After running the registor a0 became 3ffffffb40 in hexa decimal.
* Because there has -16 in decimal,so after calculation it gives the above value.

### Multiplication of first n natural numbers (C program):

**Here i have used n value as 7**

![image](https://github.com/shankargoudap/Samsung-RISC-V-Talent--Development-Program/blob/main/task2/c_code_for_mult_on_gcc_Compiler.png)

**riscv_objdump_O1_format**

* we have obtained the required main part to compare the execution in assembly language as shown below :

![image](https://github.com/shankargoudap/Samsung-RISC-V-Talent--Development-Program/blob/main/task2/Objdump_using%20-O1_format_for_mult.png)

**riscv_objdump_Ofast_format**

* we have obtained the required main part to compare the execution in assembly language as shown below :

![image](https://github.com/shankargoudap/Samsung-RISC-V-Talent--Development-Program/blob/main/task2/Objdump_using%20-Ofast_format_for_mult.png)


### Testing the SPIKE Simulator for new c program i.e mult1ton.c
**spike_O1_objdump**

* Here we are compare both of the compiler that must display the same output on the terminal.
* after that we are gona debug the sum1ton.c of **-O1_format** using SPIKE simulator

![image](https://github.com/shankargoudap/Samsung-RISC-V-Talent--Development-Program/blob/main/task2/spike_O1_objdump_for_mult1ton.png)

* In the above picture registor a2 earlier has value 1000 in hex decimal.
* After running the registor a2 became 13b0 in hexa decimal.
* Because there has +944 in decimal,so after calculation it gives the above value. 

**Spike_Ofast_objdump**

* Here also goes the same we compare both of the compiler that must display the same output on the terminal.
* after that we are gona debug the sum1ton.c of **-Ofast_format** using SPIKE simulator



![image](https://github.com/shankargoudap/Samsung-RISC-V-Talent--Development-Program/blob/main/task2/spike_Ofast_objdump_for_mult1ton.png)

* In the above picture registor a0 earlier has value 21000 in hex decimal.
* After running the registor a0 became 21180 in hexa decimal.
* Because there has +384 in decimal,so after calculation it gives the above value.

### Steps to debug spike simulation

* bring the pointer to a starting location using
```
until pc 0 100b0(loaction address uh wish to)
```
* next get the value of the registor by using
```
reg 0 a2(your registor address)
```
* next run the next intrsuction by clicking Enter key.
* after that repeat the above instruction i.e **reg 0** instruction & compare the previous value and next value.


* I have used same for both O1_format & Ofast_formate in sum1ton.c & mult1ton.c files 

### End of 2nd task
</details>

------------------------------------------------------------------------------------------------------------------

<details>
<summary><b>Task 3:</b> Task is to identify various instruction type of all the given instructions with its exact 32 bits instruction code. </summary>

### INSTRUCTIONS FORMAT IN RISC-V  
 
There are 6 instruction formats in RISC-V:  
1. R-format  
2. I-format  
3. S-format  
4. B-format  
5. U-format  
6. J-format

### 1. R-type Instruction  
* In RV32, each instruction is of size 32 bits.
* In R-type instruction, R stands for register
* This instruction type is used to execute various arithmetic and logical operations.
* The entire 32 bits instruction is divided into 6 fields as shown below.
![R-type](https://github.com/shankargoudap/Samsung-RISC-V-Talent--Development-Program/blob/main/task3/R_type_instruction.png)

### 2. I-type Instruction  
* In RV32, each instruction is of size 32 bits.
* In I-type instruction, I stand for immediate which means that operations use Registers and Immediate value
* This instruction type is used in immediate and load operations.
*  The entire 32 bits instruction is divided into 5 fields as shown below.

![I-type](https://github.com/shankargoudap/Samsung-RISC-V-Talent--Development-Program/blob/main/task3/I_type_instruction.png)

**Example: ADDI rd, rs1, imm**


### 3. S-type Instruction  

* In RV32, each instruction is of size 32 bits.
*  In S-type instruction, S stand for store which means it is store type instruction that helps to store the value of register into the memory.
*  Mainly, this instruction type is used for store operations.
*  The entire 32 bits instruction is divided into 6 fields as shown below.  
  
![s-type](https://github.com/shankargoudap/Samsung-RISC-V-Talent--Development-Program/blob/main/task3/S_type_instruction.png)

**Example: SW rs2, imm(rs1)**


### 4. B-type Instruction  
* In RV32, each instruction is of size 32 bits.
* In B-type instruction, B stand for branching which means it is mainly used for branching based on certain conditions.
*  The entire 32 bits instruction is divided into 8 fields as shown below.  
  
![B-type](https://github.com/shankargoudap/Samsung-RISC-V-Talent--Development-Program/blob/main/task3/B_type_instruction.png)

**Example: BEQ rs1, rs2, imm**   
 
  
### 5. U-type Instruction  
* In RV32, each instruction is of size 32 bits.
*  In U-type instruction, U stand for Upper Immediate instructions which means it is simply used to transfer the immediate data into the destination register.
*  The entire 32 bits instruction is divided into 3 fields as shown below.  
  
![u-type](https://github.com/shankargoudap/Samsung-RISC-V-Talent--Development-Program/blob/main/task3/U_type_instruction.png)

**Example: LUI rd, imm**   

  
### 6. J-type Instruction  
* In RV32, each instruction is of size 32 bits.
* In J-type instruction, J stand for jump, which means that this instruction format is used to implement jump type instruction.
*  The entire 32 bits instruction is divided into 6 fields as shown below.  
  
![j-type](https://github.com/shankargoudap/Samsung-RISC-V-Talent--Development-Program/blob/main/task3/J_type_instruction.png)

**Example: JAL rd, imm**

### There are 15 unique instructions from RISCV objdump application as follows:
------------------------
### 1. ADDI sp, sp, -16  

![I_type](https://github.com/user-attachments/assets/a26a328f-86e3-44bd-8197-b1d63b14179a)


> * In this instruction ADD means Addition, I means Immediate,
> * hence this instruction belongs to I-type instruction set.

- **Opcode for ADDI :** `0010011`  
- **rd = sp :** `00010`  
- **rs1 = sp :** `00010`  
- **imm[11:0] = -16 :** `111111110000`  
- **func3 :** `000`
  
**32 bits instruction :** ```111111110000|00010|000|00010|0010011``` 

--------------
### 2. SD ra 8(sp) 

![S_type](https://github.com/user-attachments/assets/eab1ca7b-f6ef-48a0-8ea5-beb055acd129)


> * In this instruction SD means store doubleword instruction,
> *  hence this instruction belongs to S-type instruction set.  
 
- **Immediate :** 000000001000 (split into imm[11:5] = 0000000 and imm[4:0] = 01000)
- **rs1 = sp :** 00010
- **rs2 = ra :** 00001
- **funct3:** 011
- **Opcode for SD :** 0100011

**32-bit instruction:** `0000000|00001|00010|011|01000|0100011`

-------------
### 3. LD ra 8(sp)

![image](https://github.com/user-attachments/assets/1c0d8506-db98-45da-b412-5e2f1180b59e)
> * In this instruction LD means  load doubleword instruction,
> *  hence this instruction belongs to S-type instruction set.

- **Immediate :** 000000001000 (split into imm[11:5] = 0000000 and imm[4:0] = 01000)
- **rs2 = ra :** 00001
- **rs1 = sp :** 00010
- **funct3:** 010 (assuming it's a store operation like `SW`)
- **Opcode for Store :** 0100011

**32-bit instruction:** `0000000|00001|00010|010|01000|0100011`

-------------------
### 4. MV a1 a0 


![image](https://github.com/user-attachments/assets/0b0164b6-a416-48d5-8602-74cea98d939f)

**The MV (Move) instruction is a pseudo-instruction in RISC-V, which is equivalent to:
ADD a1, a0, x0**

> * In this instruction MV means  pseudo-instruction,
> *  hence this instruction belongs to S-type instruction set.

- **Immediate :** 0000000 (split into imm[11:5] = 0000000 and imm[4:0] = 00000)
- **rs1 = a0 :** 01010
- **rs2 = x0 :** 00000
- **funct3:** 000
- **Opcode for ADD :** 0100011

**32-bit instruction:** `0000000|00000|01010|000|00000|0100011`


------------------------------
### 5. BEQZ a5 101f0 <exit+0x2c>

![image](https://github.com/user-attachments/assets/8e3d4a6a-59fa-4afd-be84-5b38e3c0185b)

**The BEQZ pseudo-instruction means "branch if equal to zero" and is equivalent to:
BEQ a5, x0, offset**



> * In this instruction BWQZ means  pseudo-instruction,short for "branch if equal to zero."
> *  hence this instruction belongs to B-type instruction set.

- **Immediate :** `1000000011100` (split into imm[12] = `1`, imm[10:5] = `000000`, imm[4:1] = `01110`, imm[11] = `0`)
- **rs1 = a5 :** `01111`
- **rs2 = x0 :** `00000`
- **funct3:** `000`
- **Opcode for BEQ:** `1100011`

**32-bit instruction:** `1000000|00000|01111|000|01110|1100011`

---------------------
### 6. SRAI s1 a5 0x3

![image](https://github.com/user-attachments/assets/e1236784-f266-45a2-a05e-67706beeb944)

> * In this instruction SRAI means  Shift Right Arithmetic Immediate.
> *  hence this instruction belongs to I-type instruction set.

- **Immediate :** `000000000011` (split into imm[11:0] = `000000000011`)
- **rs1 = a5 :** `01111`
- **rd = s1 :** `01001`
- **funct3:** `101`
- **Opcode for SRAI :** `0010011`

**32-bit instruction:** `000000000011|01111|101|01001|0010011`

--------------------
### 7. LUI a0 0x21 

![LUI_U_type](https://github.com/user-attachments/assets/9dcdd9ba-600f-489a-90cb-2bf6a806bbd8)


> * In this instruction LUI means Load Upper Immediate,
> *  hence this instruction belongs to U-type instruction set.

- **Immediate = 0x21 :** `0000000000000_00100001`
- **rd = a5:** `01010`
- **Opcode:** `0110111`

**32 bits instruction :** ```0000000000000|00100001|01010|0110111``` 

--------------------------
### 8. JAL ra 10408 <printf>

![JAL_J_type](https://github.com/user-attachments/assets/e6aee0d7-2236-4d33-a7ef-9ddfece0cae9)


> * In this instruction JAL means Jump and Link,
> *  hence this instruction belongs to J-type instruction set.

- **Immediate (20 bits)**: `0 1001100000 1 00001010` (split into imm[20] = `0` and imm[10:1] = `1001100000 `imm[11] = `1` and imm[19:12] = `00001010`)
- **rd (ra = x1)**: `00001`
- **Opcode**: `1101111`
		         
**32 bits instruction :** ```0 1001100000 1 00001010|00001|1101111```

------------------
### 9. AUIPC a5 0xffff0

![image](https://github.com/user-attachments/assets/dc1b9458-2bce-4ea9-89c1-610b5170cd78)

> * In this instruction AUIPC means Add Upper Immediate to PC Immediate,
> *  hence this instruction belongs to U-type instruction set.

- **Immediate :** 11111111111100000000 (split into imm[31:12] = 111111111111 and imm[11:0] = 000000000000)
- **rd = a5 :** `01111`
- **Opcode for AUIPC :** `0010111`

**32-bit instruction:** `111111111111|01111|0010111`

-----------------------
### 10. J 101b0 <atexit> 

![image](https://github.com/user-attachments/assets/d837a001-3588-4ea7-9627-851fb5ff4cc3)

> * In this instruction J means Jump and Link,
> *  hence this instruction belongs to J-type instruction set.

- **Immediate :** `0000010000001101010` (split into imm[20] = `0`, imm[10:1] = `0000000000`, imm[11] = `0`, imm[19:12] = `00000100`)
- **rd = x0 :** `00000`
- **Opcode for J-type (JAL):** `1101111`

**32-bit instruction:** `0000000|0000000000|0|00000100|00000|1101111`

------------------
### 11. LW a0 0(sp)

![image](https://github.com/user-attachments/assets/8aa35f2b-bcd2-4619-a3dd-d22d0f706dff)

> * In this instruction, LW means Load Word,
> * hence this instruction belongs to I-type instruction set.

- **Immediate :** `000000000000`
- **rs1 = sp :** `00010`
- **rd = a0 :** `01010`
- **funct3:** `010`
- **Opcode for LW :** `0000011`

**32-bit instruction:** `000000000000|00010|010|01010|0000011`

---------------------
### 12. BENZ a5,10188 <do global dtors aux+0x4c>
    
![image](https://github.com/user-attachments/assets/31d8c899-4b38-4779-95d8-ed01a5ca0023)

**Assume that BENZ behaves similarly to a branch instruction, but with a custom format. We can treat BENZ like a branch if not zero instruction**

> * In this instruction BENZ means a specific operation (hypothetical or custom instruction), 
> * hence this instruction belongs to a custom instruction type.

- **Immediate :** `0000011010010` (split into imm[12] = `0`, imm[10:5] = `000001`, imm[4:1] = `1010`, imm[11] = `0`)
- **rs1 = a5 :** `01111`
- **rs2 = x0 :** `00000`
- **funct3:** `001`
- **Opcode for custom BENZ:** `1100011`

**32-bit instruction:** `0000001|00000|01111|001|1010|1100011`

------------------------------------------------
### 13. LBU a5, 1944(gp) # 231a0 <completed.5468>

![image](https://github.com/user-attachments/assets/8f009b1b-1992-45c9-a6ee-aab390d88532)

> * In this instruction LBU means Load Byte Unsigned,
> * hence this instruction belongs to I-type instruction set

- **Immediate :** `11110001000`
- **rs1 = gp :** `00011`
- **rd = a5 :** `01111`
- **funct3:** `100`
- **Opcode for LBU:** `0000011`

**32-bit instruction:** `11110001000|00011|100|01111|0000011`

--------------------
### 14. LI a0 0

![image](https://github.com/user-attachments/assets/732699d9-8bdf-48e5-bbce-ff775e79ea57)

**The LI pseudo-instruction means "Load Immediate" and is equivalent to an ADDI (Add Immediate) instruction** 

> * In this instruction LI means Load Immediate,
> * hence this instruction belongs to I-type instruction set

- **Immediate :** `000000000000` (12 bits)
- **rs1 = x0 :** 00000`
- **rd = a0 :** 01010`
- **funct3:** 000`
- **Opcode for ADDI:** `0010011`

**32-bit instruction:** `000000000000|00000|000|01010|0010011`

-----------------------------
### 15. SLLI t0, t0,0x1f

![image](https://github.com/user-attachments/assets/caf27b0e-ce37-48a5-b43f-d278bd3c3c11)

> * In this instruction, SLLI means Shift Left Logical Immediate,
> *hence this instruction belongs to the I-type instruction set.

- **Immediate :** `000000011111` (12-bit immediate value for 0x1f)
- **rs1 = t0 :** `00101`
- **rd = to :** `00110`
- **funct3:** `001`
- **Opcode for SLLI :** `0010011`

**32-bit instruction:** `000000011111|00101|001|00110|0010011`

### End of 3rd task
</details>

------------------------------------------------------------------------------------------------------------------


<details>
<summary><b>Task 4:</b> Use this RISC-V Core Verilog netlist and testbench for functional simulation experiment. Upload waveform snapshots for the commands on your GitHub. </summary>

Reference GitHub repo is [![GitHub](https://img.shields.io/badge/-GitHub-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/shankargoudap/Samsung-RISC-V-Talent--Development-Program/rv32i/blob/main/iiitb_rv32i.v)

## Starting with Functional Simulation
* First I installed the iverilog and gtkwave using following commands:
  ```
  sudo apt-get update
  ```
  ```
  sudo apt-get install iverilog gtkwave
  ```
* Cloning the github repository:
  - make a github repository
  - upload the two filies
  - 1. https://github.com/shankargoudap/Samsung-RISC-V-Talent--Development-Program/blob/main/iiitb_rv32i.v
    2. https://github.com/shankargoudap/Samsung-RISC-V-Talent--Development-Program/blob/main/iiitb_rv32i_tb.v
  -  run the below code in cmd 

  ```
   git clone https://github.com/shankargoudap/Samsung-RISC-V-Talent--Development-Program
   ```

* Chanding the working directory to `shankaru` using the following comand:
  ```
   cd shankaru
  ```

* To simulate and run the verilog code , entered the following commands in the terminal:
  ```
  iverilog -o shankaru iiitb_rv32i.v iiitb_rv32i_tb.v
  ```
  ```
  ./shankaru
  ```
* For seeing the output waveform I used the following command:
  ```
  gtkwave iiitb_rv32i.vcd
  ```

* The GTKWave will be opened and following window will be appeared  
  
![image](https://github.com/user-attachments/assets/8ebb8c40-d549-4bd2-9521-92a4200b617c)

### As shown in the figure below, all the instructions in the given verilog file is hard-coded, the designer has hard-coded each instructions based on their own pattern. Hence the 32-bits instruction that we generated in above task will not match with the given instruction.

![image](https://github.com/user-attachments/assets/512edc06-4524-43f7-833f-e3d087869a38)

#### Following are the differences between standard RISCV ISA and the Instruction Set given in the reference repository:  
  
|  **Operation**  |  **Standard RISCV ISA**  |  **Hardcoded ISA**  |  
|  :----:  |  :----:  |  :----:  |  
|  ADD R6, R2, R1  |  32'h00110333  |  32'h02208300  |  
|  SUB R7, R1, R2  |  32'h402083b3  |  32'h02209380  |  
|  AND R8, R1, R3  |  32'h0030f433  |  32'h0230a400  |  
|  OR R9, R2, R5  |  32'h005164b3  |  32'h02513480  |  
|  XOR R10, R1, R4  |  32'h0040c533  |  32'h0240c500  |  
|  SLT R1, R2, R4  |  32'h0045a0b3  |  32'h02415580  |  
|  ADDI R12, R4, 5  |  32'h004120b3  |  32'h00520600  |  
|  BEQ R0, R0, 15  |  32'h00000f63  |  32'h00f00002  |  
|  SW R3, R1, 2  |  32'h0030a123  |  32'h00209181  |  
|  LW R13, R1, 2  |  32'h0020a683  |  32'h00208681  |  
|  SRL R16, R14, R2  |  32'h0030a123  |  32'h00271803  |
|  SLL R15, R1, R2  |  32'h002097b3  |  32'h00208783  |  

### Instruction 1. ADD 

![image](https://github.com/user-attachments/assets/f1b4a40d-b584-4fde-bb48-2132a76a858d)

### Detailed Explanation:
- **Values Stored in Two Different Registers**:
  - The waveform indicates that the values `1` and `2` are stored in registers `r1` and `r2` respectively (`ID_EX_A` and `ID_EX_B`).

- **32-bit Instruction for ADD `R6, R2, R1`**:
  - The instruction `0x02208300` represents the operation `add r6, r1, r2`. This instruction tells the processor to add the values in registers `r1` and `r2` and store the result in register `r6`.

- **Output of ADD Operation**:
  - The ALU performs the addition `1 + 2`, resulting in `3`, which is shown in the `EX_MEM_ALUOUT` signal.

### Instruction 2. SUB

![image](https://github.com/user-attachments/assets/8ae77a86-82ae-4b89-93cc-0e5e060876b7)


### Detailed Explanation:
- **Values Stored in Two Different Registers**:
  - The waveform indicates that the values `1` and `2` are stored in registers `r1` and `r2` respectively (`ID_EX_A` and `ID_EX_B`).

- **32-bit Instruction for SUB `R7, R2, R1`**:
  - The instruction `0x02208380` represents the operation `sub r7, r1, r2`. This instruction tells the processor to add the values in registers `r1` and `r2` and store the result in register `r7`.

- **Output of ADD Operation**:
  - The ALU performs the addition `1 - 2`, resulting in `-1(FFFFFFFF)`, which is shown in the `EX_MEM_ALUOUT` signal.

### Instruction 3. AND

![image](https://github.com/user-attachments/assets/d8438554-d42e-4585-96de-55d731174ad8)


#### Key Points:
1. **Values Stored in Registers**:
   - `ID_EX_A` holds `3`, corresponding to the value in register `R1`.
   - `ID_EX_B` holds `1`, corresponding to the value in register `R3`.

2. **Instruction Fetching**:
   - `EX_MEM_IR` signal shows the value `0x0230A400`, which is the 32-bit instruction for `AND R8, R1, R3`.

3. **ALU Operation**:
   - The output of the ALU operation `EX_MEM_ALUOUT` shows `1`. This is the result of the bitwise AND operation `3 & 1`:
     - `3` in binary is `0011`
     - `1` in binary is `0001`
     - Bitwise AND of `0011 & 0001` results in `0001`, which is `1` in decimal.

4. **Steps in the Processor Pipeline**:
   - **Fetch Stage**: Instruction `AND R8, R1, R3` is fetched.
   - **Decode Stage**: The values of `R1` and `R3` are read into `ID_EX_A` and `ID_EX_B`.
   - **Execute Stage**: The ALU performs the bitwise AND operation, resulting in `1`.
   - **Memory and Write Back Stages**: (Not shown explicitly but understood to follow.)

### Instruction 4. OR 

![image](https://github.com/user-attachments/assets/5282ec13-2fd0-4a2a-9bd0-fa6dd565709a)


**Description:**
- This instruction performs a bitwise OR operation between the values in registers R2 and R5 and stores the result in register R9.

**Details:**
- The values in R2 and R5 are `2` (binary: `0010`) and `5` (binary: `0101`), respectively.
- The bitwise OR operation (`0010 | 0101`) results in `7` (binary: `0111`).


### Instruction 5. XOR

![image](https://github.com/user-attachments/assets/c385fa51-f561-4293-b971-838145925155)


**Description:**
- This instruction performs a bitwise XOR operation between the values in registers R1 and R4 and stores the result in register R10.

**Details:**
- The values in R1 and R4 are `1` (binary: `0001`) and `4` (binary: `0100`), respectively.
- The bitwise XOR operation (`0001 ^ 0100`) results in `5` (binary: `0101`).


### Instruction 6. SLT 

![Screenshot 2025-01-22 224702](https://github.com/user-attachments/assets/683dafb3-af55-409b-949e-89f8655a6296)

1. **Instruction**: `SLT R1, R2, R4`
   - This instruction performs a "Set Less Than" (SLT) operation. It compares the values in registers `R2` and `R4` and sets the destination register `R1` to 1 if the value in `R2` is less than the value in `R4`; otherwise, it sets `R1` to 0.

2. **Waveform Signals**:
   - **EX_MEM_IR[31:0]**: The instruction register for the Execution/Memory (EX/MEM) pipeline stage, holding the 32-bit instruction `0x202415580`.
   - **ID_EX_A[31:0]**: The value of register `R2`.
   - **ID_EX_B[31:0]**: The value of register `R4`.
   - **EX_MEM_ALUOUT[31:0]**: The output of the Arithmetic Logic Unit (ALU) after performing the SLT operation.

3. **Waveform Details**:
   - **Values in Registers**: The values stored in `R2` and `R4` are 2 and 4, respectively.
   - **SLT Operation**: The SLT operation compares these values. Since 2 < 4, the output is 1, indicating `R2` is less than `R4`.

4. **Annotations**:
   - **Values stored in two different registers**: Highlighting the values of `R2` and `R4`.
   - **Output of SLT will be 1**: Explains that if the value in `R2` is less than `R4`, the result will be 1; otherwise, it will be 0.
   - **32 bits instruction for SLT R1, R2, R4**: Shows the binary representation of the SLT instruction.

### Instruction 7. ADDI 

![image](https://github.com/user-attachments/assets/4317b78c-4289-42af-9d2a-e867f904b3f2)

1. **Instruction**: `ADDI R12, R4, 5`
   - This instruction performs an "Add Immediate" (ADDI) operation. It adds the immediate value 5 to the value in register `R4` and stores the result in register `R12`.

2. **Waveform Signals**:
   - **EX_MEM_IR[31:0]**: The instruction register for the Execution/Memory (EX/MEM) pipeline stage, holding the 32-bit instruction `0x00520600`.
   - **ID_EX_A[31:0]**: The value of register `R4`.
   - **ID_EX_IMMEDIATE[31:0]**: The immediate value 5.
   - **EX_MEM_ALUOUT[31:0]**: The output of the ALU after performing the ADDI operation.

3. **Waveform Details**:
   - **Values in Registers and Immediate**: The value stored in `R4` is 4, and the immediate value is 5.
   - **ADDI Operation**: The ADDI operation adds these values. The result is 9, which is stored in `R12`.

4. **Annotations**:
   - **Stored value in Register and an Immediate value**: Highlights the values involved in the ADDI operation.
   - **Output of ADDI will be 9**: Explains that the value in `R4` (4) added to the immediate value (5) results in 9.
   - **32 bits instruction for ADDI R12, R4, 5**: Shows the binary representation of the ADDI instruction.

### Instruction 8. BEQ 

![image](https://github.com/user-attachments/assets/fae591e8-7c12-4cd5-8069-feab798b8710)

**Description:**
- The `BEQ` (Branch if Equal) instruction compares the values in registers `R0` and `R0`.
- If the values are equal, it adds the immediate value `15` to the program counter (PC).

**Waveform Analysis:**
- **Initial State:** The program counter (PC) is initially at `10`.
- **Registers:** Both `R0` registers contain the value `0`.
- **Condition:** Since `R0` is equal to `R0`, the condition is true.
- **PC Update:** The instruction adds `15` to the PC.
  - PC = 10(0A in hexa) + 15 = 25(19 in hexa) .
- **Result:** The updated PC value is `25(19 in hexa)`.


### Instruction 9. BNE 

![image](https://github.com/user-attachments/assets/6aa52a22-cf8b-4d19-9433-6bbc8038afd6)

**Description:**
- The `BEQ` (Branch if not Equal) instruction compares the values in registers `R0` and `R0`.
- If the values are not equal, it adds the immediate value `20` to the program counter (PC).

**Waveform Analysis:**
- **Initial State:** The program counter (PC) is initially at `10`.
- **Registers:** Both `R0` registers contain the value `0`.
- **Condition:** Since `R0` is equal to `R0`, the condition is true.
- **PC Update:** The instruction adds `20` to the PC.
  - PC = 26(1A in hexa) + 20 = 46(2E in hexa) .
- **Result:** The updated PC value is `46(2E in hexa)`.

### Instruction 10. SLL

![image](https://github.com/user-attachments/assets/94fd2459-651d-456e-890d-6103cb0b658b)

### End of 4th task
</details>

------------------------------------------------------------------------------------------------------------------

<details>
   <summary><b>Task 5:Overview, Components Required, Circuit Connection, Pinout Diagram and Table for Pin connection required to build the display driver.</summary>

# Developing a 7 segment display driver using VSDSquadron Mini

## Overview
The project presents an innovative integration of CH32V003 RISC-V processor to create a 7 segment LED display driver. The processor decodes the given number into its binary counterpart and according to the bits it gives signal to each segment whether it should glow or not. Thus, instead of setting the display manually everytime we can automate it. Currently we are driving only one display, future works will include integrating 2 displays together.

## Components Required
* VSDSquadron Mini
* 1 seven segment display
* Breadboard
* Power Supply
* Jumper Wires
* Resistors

## Circuit Connection
* Connect the Common Anode/Cathode pin to VCC or GND via a resistor depending on the type of display.
* Connect `PD0` to pin `a` of the display.
* Connect `PC0` to pin `b` of the display.
* Connect `PD2` to pin `c` of the display.
* Connect `PD3` to pin `d` of the display.
* Connect `PD4` to pin `e` of the display.
* Connect `PD5` to pin `f` of the display.
* Connect `PD6` to pin `g` of the display.

The above pins recives the signals the on/off signals for the segments.

## Pinout Diagram for the project
The following diagram is for Common Cathode seven segment led:

![diagram](https://github.com/user-attachments/assets/3f48ed70-0a26-402d-acac-4975a63a9954)



## Table for Pin connection
| SEVEN SEGMENT  | RISC-V |
| -------------- | ------ |
| a              | PD0    |
| b              | PC0    |
| c              | PD2    |
| d              | PD3    |
| e              | PD4    |
| f              | PD5    |
| g              | PD6    |
| CA/CC          | VCC/GND|

## Code uploaded on the board
```
#include <ch32v00x.h>
#include <debug.h>

// Define the GPIO pins for the driver
#define a GPIO_Pin_0        // Pin for segment a
#define b GPIO_Pin_1        // Pin for segment b (corrected to a different pin)
#define c GPIO_Pin_2        // Pin for segment c
#define d GPIO_Pin_3        // Pin for segment d      
#define e GPIO_Pin_4        // Pin for segment e    
#define f GPIO_Pin_5        // Pin for segment f    
#define g GPIO_Pin_6        // Pin for segment g    

int outar[] = {0, 0, 0, 0, 0, 0, 0};
int out[] = {126, 48, 109, 121, 51, 91, 95, 112, 127, 123, 119, 31, 78, 61, 79, 71};

// Function prototypes
void GPIO_Config(void);
void assign(int);

// GPIO configuration function
void GPIO_Config(void) {
    GPIO_InitTypeDef GPIO_InitStructure = {0};

    RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOD, ENABLE); // Enable clock for Port D
    RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOC, ENABLE); // Enable clock for Port C

    // Configure pin a as output
    GPIO_InitStructure.GPIO_Pin = a;
    GPIO_InitStructure.GPIO_Mode = GPIO_Mode_Out_PP;
    GPIO_InitStructure.GPIO_Speed = GPIO_Speed_50MHz;
    GPIO_Init(GPIOD, &GPIO_InitStructure);

    // Configure pin b as output
    GPIO_InitStructure.GPIO_Pin = b;
    GPIO_Init(GPIOC, &GPIO_InitStructure);

    // Configure pin c as output
    GPIO_InitStructure.GPIO_Pin = c;
    GPIO_Init(GPIOD, &GPIO_InitStructure);

    // Configure pin d as output
    GPIO_InitStructure.GPIO_Pin = d;
    GPIO_Init(GPIOD, &GPIO_InitStructure);

    // Configure pin e as output
    GPIO_InitStructure.GPIO_Pin = e;
    GPIO_Init(GPIOD, &GPIO_InitStructure);

    // Configure pin f as output
    GPIO_InitStructure.GPIO_Pin = f;
    GPIO_Init(GPIOD, &GPIO_InitStructure);

    // Configure pin g as output
    GPIO_InitStructure.GPIO_Pin = g;
    GPIO_Init(GPIOD, &GPIO_InitStructure);
}

int main() {
    // SystemCoreClockUpdate(); // Uncomment if needed
    Delay_Init();
    GPIO_Config();
    
    while (1) {
        for (int i = 0; i < 16; i++) {
            assign(i);
            
            // Set the GPIO pins based on the outar array
            GPIO_WriteBit(GPIOD, a, outar[6] ? SET : RESET);
            GPIO_WriteBit(GPIOC, b, outar[5] ? SET : RESET);
            GPIO_WriteBit(GPIOD, c, outar[4] ? SET : RESET);
            GPIO_WriteBit(GPIOD, d, outar[3] ? SET : RESET);
            GPIO_WriteBit(GPIOD, e, outar[2] ? SET : RESET);
            GPIO_WriteBit(GPIOD, f, outar[1] ? SET : RESET);
            GPIO_WriteBit(GPIOD, g, outar[0] ? SET : RESET);
            
            Delay_Ms(5000); // Delay for 5 seconds
        }
    }
}

void assign(int num) {
    int mask = 1;
    for (int i = 0; i < 7; i++) {
        outar[i] = (mask & out[num]) ? 1 : 0; // Set outar based on the current number
        mask = mask << 1; // Shift the mask to check the next bit
    }
}
```
---------------------------------------------------------------
## Final_project

#task 4
=

# MAKING A GAME COSOLE USING VSDSQUADRON MINI

![f575878f-6447-4391-aa24-13d8dac9a91f](https://github.com/NavaneethKumar237/Risc-v-internship/assets/167600626/1f3854c4-914c-476d-86c1-c3d3075f5d26)

INTRODUCTION
-


A game console is a device used to connect to a display for playing games. I have developed a game console using the VSDSquadron Mini. We used an OLED display to view the games, making it possible to play games directly on this compact and efficient setup. This application showcases the capabilities of the VSDSquadron Mini.

OVERVIEW
-
This is a smiple model of the game console had 5 push buttons and oled disply to show and a power switch 
we need to connect all the all the components to vsdsquadron mini we have to upload the specific code in to it to get the desired game
The heart of the game console is a RISC-V based microcontroller based vsd mini board  , providing an open-source, highly efficient, and customizable platform for many applications.

------------------------------------------------------------
LIST OF COMPONENTS
-
1. VSDsquadron mini 
2. 5 push buttons
3. zero PCB
4. jumper  wires
5. OLED display
6. Resistors of differnt values

HARDWARE CONNECTIONS
=
---------------------------------------------------------

CIRCUIT DIAGRAM
-

![f575878f-6447-4391-aa24-13d8dac9a91f](https://github.com/NavaneethKumar237/Risc-v-internship/assets/167600626/1f3854c4-914c-476d-86c1-c3d3075f5d26)


PINOUT
-
 ![image](https://github.com/NavaneethKumar237/Risc-v-internship/assets/167600626/90fd5f59-ad37-4515-8948-5095136b599a)

![image](https://github.com/NavaneethKumar237/Risc-v-internship/assets/167600626/251a0b5a-1739-4686-b5a4-379f28fa29b0)


SOFTWARE REQUIREMENTS
=
I have used the linux to upload the code we need to install the required tools related to the risc-v 
next you need to Install the toolchain (GCC compiler, Python3, and PyUSB):

```sudo apt install build-essential libnewlib-dev gcc-riscv64-unknown-elf
sudo apt install python3 python3-pip
python3 -m pip install pyus
```

 Open a terminal and navigate to the folder with the makefile. Run the following command to compile and upload:
 ```
make flash
 ```
If you want to just upload the pre-compiled binary, run the following command instead:

```
python3 .tools/rvprog.py -f <firmware>.bin
```

Working code
-





```

#include <driver.h>           // TinyJoypad conversion driver
#include <spritebank.h>       // grafix

// ===================================================================================
// Global Variables
// ===================================================================================
uint8_t Live = 0;
uint8_t ShieldRemoved = 0;
uint8_t MONSTERrest = 0;
uint8_t LEVELS = 0;
uint8_t SpeedShootMonster = 0;
uint8_t ShipDead = 0;
uint8_t ShipPos = 56;

#define SHOOTS 2

// ===================================================================================
// Function Prototypes
// ===================================================================================
void LoadMonstersLevels(int8_t Levels, SPACE *space);
void SnD(int8_t Sp_, uint8_t SN);
void SpeedControle(SPACE *space);
void GRIDMonsterFloorY(SPACE *space);
uint8_t LivePrint(uint8_t x, uint8_t y);
void Tiny_Flip(uint8_t render0_picture1, SPACE *space);
uint8_t UFOWrite(uint8_t x, uint8_t y, SPACE *space);
void UFOUpdate(SPACE *space);
void ShipDestroyByMonster(SPACE *space);
void MonsterShootupdate(SPACE *space);
void MonsterShootGenerate(SPACE *space);
uint8_t MonsterShoot(uint8_t x, uint8_t y, SPACE *space);
uint8_t ShieldDestroy(uint8_t Origine, uint8_t VarX, uint8_t VarY, SPACE *space);
void ShieldDestroyWrite(uint8_t BOOLWRITE, uint8_t line, SPACE *space, uint8_t Origine);
uint8_t MyShield(uint8_t x, uint8_t y, SPACE *space);
uint8_t ShieldBlitz(uint8_t Part, uint8_t LineSH);
uint8_t BOOLREAD(uint8_t SHnum, uint8_t LineSH, SPACE *space);
void RemoveExplodOnMonsterGrid(SPACE *space);
uint8_t background(uint8_t x, uint8_t y, SPACE *space);
uint8_t Vesso(uint8_t x, uint8_t y, SPACE *space);
void UFO_Attack_Check(uint8_t x, SPACE *space);
uint8_t MyShoot(uint8_t x, uint8_t y, SPACE *space);
void Monster_Attack_Check(SPACE *space);
int8_t OuDansLaGrilleMonster(uint8_t x, uint8_t y, SPACE *space);
uint8_t SplitSpriteDecalageY(uint8_t Input, uint8_t UPorDOWN, SPACE *space);
uint8_t Murge_Split_UP_DOWN(uint8_t x, SPACE *space);
uint8_t WriteMonster14(uint8_t x);
uint8_t Monster(uint8_t x, uint8_t y, SPACE *space);
uint8_t MonsterRefreshMove(SPACE *space);
void VarResetNewLevel(SPACE *space);

// ===================================================================================
// Main Function
// ===================================================================================
int main(void) {
  // Setup
  JOY_init();

  // Loop
  while(1) {
    uint8_t Decompte = 0;
    uint8_t VarPot;
    uint8_t MyShootReady = SHOOTS;
    SPACE space;

  NEWGAME:
    Live = 3;
    LEVELS = 0;
    Tiny_Flip(1, &space);
    while(1) {
      if(JOY_act_pressed()) {
        JOY_sound(100, 125); JOY_sound(50, 125);
        goto BYPASS2;
      }
    }

  NEWLEVEL:
    JOY_DLY_ms(1000);

  BYPASS2:
    VarResetNewLevel(&space);
    SpeedControle(&space);
    VarPot = 54;
    ShipPos = 56;
    space.ScrBackV=(ShipPos / 14) + 52;
    goto Bypass;

  RestartLevel:
    if(Live > 0) Live--;
    else goto NEWGAME;

  Bypass:
    ShipDead = 0;
    Decompte = 0;
    Tiny_Flip(0, &space);
    JOY_DLY_ms(1000);
    while(1) {
      if(MONSTERrest == 0) { 
        JOY_sound(110, 255); JOY_DLY_ms(40); JOY_sound(130, 255); JOY_DLY_ms(40);
        JOY_sound(100, 255); JOY_DLY_ms(40); JOY_sound(1, 155);   JOY_DLY_ms(20);
        JOY_sound(60, 255);  JOY_sound(60, 255);
        if(LEVELS < 9) LEVELS++;
        goto NEWLEVEL;
      }
      if((((space.MonsterGroupeYpos) + (space.MonsterFloorMax + 1)) == 7) && (Decompte == 0)) ShipDead = 1;
      if(SpeedShootMonster <= 9 - LEVELS) SpeedShootMonster++;
      else {SpeedShootMonster = 0; MonsterShootGenerate(&space);}
      space.ScrBackV = (ShipPos / 14) + 52;
      Tiny_Flip(0, &space);
      space.oneFrame = !space.oneFrame;
      RemoveExplodOnMonsterGrid(&space);
      MonsterShootupdate(&space);
      UFOUpdate(&space);
      if(((space.MonsterGroupeXpos >= 26) && (space.MonsterGroupeXpos <= 28))
        && (space.MonsterGroupeYpos == 2) && (space.DecalageY8 == 4)) space.UFOxPos = 127;
      if(VarPot > (ShipPos + 2)) ShipPos = ShipPos + ((VarPot - ShipPos) / 3);
      if(VarPot < (ShipPos - 2)) ShipPos = ShipPos - ((ShipPos - VarPot) / 3);
      if(ShipDead != 1) {
        if(space.frame < space.frameMax) space.frame++;
        else {
          GRIDMonsterFloorY(&space);
          space.anim = !space.anim;
          if(space.anim == 0) SnD(space.UFOxPos, 200);
          else SnD(space.UFOxPos, 100);
          MonsterRefreshMove(&space);
          space.frame = 0;
        }

        if(JOY_left_pressed()) {
          if(VarPot > 5) VarPot = VarPot - 6;
        }
        if(JOY_right_pressed()) {
          if(VarPot < 108) VarPot = VarPot + 6;
        }
        if((JOY_act_pressed()) && (MyShootReady == SHOOTS)) {
          JOY_sound(200, 4); MyShootReady = 0; space.MyShootBall = 6; space.MyShootBallxpos = ShipPos + 6;
        }
      }
      else {
        JOY_sound(80, 1); JOY_sound(100, 1); 
        Decompte++;
        if(Decompte >= 30) {
          JOY_DLY_ms(600);
          if(((space.MonsterGroupeYpos) + (space.MonsterFloorMax + 1)) == 7) goto NEWGAME;
          else goto RestartLevel;
        }
      }
      if(space.MyShootBall == -1) {
        if(MyShootReady<SHOOTS) MyShootReady++;
      }
    JOY_SLOWDOWN();
    }
  }
}

// ===================================================================================
// Functions
// ===================================================================================
void LoadMonstersLevels(int8_t Levels, SPACE *space) {
  uint8_t x, y;
  for(y=0; y<5; y++) {
    for(x=0; x<6; x++) {
      if(y!=4) space->MonsterGrid[y][x] = MonstersLevels[(Levels * 24) + (y * 6) + x];
      else     space->MonsterGrid[y][x] = -1;
    }
  }
}

void SnD(int8_t Sp_, uint8_t SN) {
  if(Sp_ != -120) {JOY_sound(220, 8); JOY_sound(200, 4);}
  else JOY_sound(SN, 1);
}

void SpeedControle(SPACE *space) {
  uint8_t xx, yy;
  MONSTERrest = 0;
  for(yy=0; yy<4; yy++) {
    for(xx=0; xx<6; xx++) {
      if((space->MonsterGrid[yy][xx] != -1) && ((space->MonsterGrid[yy][xx] <=5 ))) MONSTERrest++;
    }
  }
  space->frameMax = (MONSTERrest >> 3);
}

// Thanks to Sven Bruns for informing me of an error in this function!
void GRIDMonsterFloorY(SPACE *space) {
  uint8_t y,x;
  space->MonsterFloorMax = 3;
  for(y=0; y<4; y++) {
    for(x=0; x<6; x++) {
      if(space->MonsterGrid[3-y][x] != -1) return;
    }
    space->MonsterFloorMax = space->MonsterFloorMax - 1;
  }
}

uint8_t LivePrint(uint8_t x, uint8_t y) {
  #define XLIVEWIDE ((5 * Live) - 1)
  if((0 >= (x - XLIVEWIDE)) && (y == 7)) {
    return LIVE[x];
  }
  return 0x00;
}

void Tiny_Flip(uint8_t render0_picture1, SPACE *space) {
  uint8_t y, x; 
  uint8_t MYSHIELD = 0x00;
  for(y=0; y<8; y++) {
    JOY_OLED_data_start(y);
    for(x=0; x<128; x++) {
      if(render0_picture1 == 0) {
        if(ShieldRemoved == 0) MYSHIELD = MyShield(x, y, space);
        else MYSHIELD = 0x00;
        JOY_OLED_send( background(x, y, space)
                       | LivePrint(x, y) 
                       | Vesso(x, y, space)
                       | UFOWrite(x, y, space)
                       | Monster(x, y, space)
                       | MyShoot(x, y, space)
                       | MonsterShoot(x, y, space)
                       | MYSHIELD);
      }
      else JOY_OLED_send(intro[x + (y * 128)]);
    }
    if(render0_picture1 == 0) {
      if(ShieldRemoved == 0) ShieldDestroy(0, space->MyShootBallxpos, space->MyShootBall, space);
    }
    JOY_OLED_end();
  }
  if(render0_picture1 == 0) {
    if(!(space->MonsterGroupeYpos < (2 + (4 - (space->MonsterFloorMax + 1))))) {
      if(ShieldRemoved != 1) {
        space->Shield[0] = 0x00;
        space->Shield[1] = 0x00;
        space->Shield[2] = 0x00;
        space->Shield[3] = 0x00;
        space->Shield[4] = 0x00;
        space->Shield[5] = 0x00;
        ShieldRemoved = 1;
      }
    }
  }
}

uint8_t UFOWrite(uint8_t x, uint8_t y, SPACE *space) {
  if((space->UFOxPos != -120) && (y == 0) && (space->UFOxPos <= x) && (space->UFOxPos >= (x - 14)))
    return Monsters[(x - space->UFOxPos) + (6 * 14) + (space->oneFrame * 14)];
  return 0x00;
}

void UFOUpdate(SPACE *space) {
  if(space->UFOxPos != -120) {
    space->UFOxPos = space->UFOxPos - 2;
    SnD(space->UFOxPos, 0);
    if(space->UFOxPos <= -20) space->UFOxPos = -120;
  }
}

void ShipDestroyByMonster(SPACE *space) {
  if((space->MonsterShoot[1] >= 14) && (space->MonsterShoot[1] <= 15) 
  && (space->MonsterShoot[0] >= ShipPos) && (space->MonsterShoot[0] <= ShipPos+14))
    ShipDead=1;
}

void MonsterShootupdate(SPACE *space) {
  if(space->MonsterShoot[1] != 16) {
    ShipDestroyByMonster(space);
    if(ShieldDestroy(1, space->MonsterShoot[0], space->MonsterShoot[1] >> 1, space))
      space->MonsterShoot[1] = 16;
    else
      space->MonsterShoot[1] = space->MonsterShoot[1] + 1;
  }
}

void MonsterShootGenerate(SPACE *space) {
  uint8_t a = JOY_random() % 3; 
  uint8_t b = JOY_random() % 6; 
  if(b >= 5) b = 5;
  if(space->MonsterShoot[1] == 16) {
    if(space->MonsterGrid[a][b] != -1) {
      space->MonsterShoot[0] = (space->MonsterGroupeXpos + 7) + (b * 14);
      space->MonsterShoot[1] = ((space->MonsterGroupeYpos + a) * 2) + 1;
    }
  }
}

uint8_t MonsterShoot(uint8_t x, uint8_t y, SPACE *space) {
  if(((space->MonsterShoot[1] >> 1) == y) && (space->MonsterShoot[0] == x)) {
    if((space->MonsterShoot[1] & 1) == 0) return 0b00001111;
    else return 0b11110000;
  }
  return 0x00;
}

uint8_t ShieldDestroy(uint8_t Origine, uint8_t VarX, uint8_t VarY, SPACE *space) {
  #define OFFSETXSHIELD -1
  if(VarY == 6) {
    if((VarX >= 20 + OFFSETXSHIELD) && (VarX <= 27 + OFFSETXSHIELD)) {
      if(BOOLREAD(0, VarX - (20 + OFFSETXSHIELD), space)) {
        ShieldDestroyWrite(0, VarX - (20 + OFFSETXSHIELD), space, Origine);
        return 1;
      }
    }
    if((VarX >= 28 + OFFSETXSHIELD) && (VarX <= 35 + OFFSETXSHIELD)) {
      if(BOOLREAD(1, VarX - (28 + OFFSETXSHIELD), space)) {
        ShieldDestroyWrite(1, VarX - (28 + OFFSETXSHIELD), space, Origine);
        return 1;
      }
    }
    if((VarX >= 55 + OFFSETXSHIELD) && (VarX <= 62 + OFFSETXSHIELD)) {
      if(BOOLREAD(2, VarX - (55 + OFFSETXSHIELD), space)) {
        ShieldDestroyWrite(2, VarX - (55 + OFFSETXSHIELD), space, Origine);
        return 1;
      }
    }
    if((VarX >= 63 + OFFSETXSHIELD) && (VarX <= 70 + OFFSETXSHIELD)) {
      if(BOOLREAD(3, VarX - (63 + OFFSETXSHIELD), space)) {
        ShieldDestroyWrite(3, VarX - (63 + OFFSETXSHIELD), space, Origine);
        return 1;
      }
    }
    if((VarX >= 90 + OFFSETXSHIELD) && (VarX <= 97 + OFFSETXSHIELD)) {
      if(BOOLREAD(4, VarX - (90 + OFFSETXSHIELD), space)) {
        ShieldDestroyWrite(4, VarX - (90 + OFFSETXSHIELD), space, Origine);
        return 1;
      }
    }
    if((VarX >= 98 + OFFSETXSHIELD) && (VarX <= 105 + OFFSETXSHIELD)) {
      if(BOOLREAD(5, VarX - (98 + OFFSETXSHIELD), space)) {
        ShieldDestroyWrite(5, VarX - (98 + OFFSETXSHIELD), space, Origine);
        return 1;
      }
    }
  }
  return 0;
}

void ShieldDestroyWrite(uint8_t BOOLWRITE, uint8_t line, SPACE *space, uint8_t Origine) {
  switch(line) {
    case 0:
      space->Shield[BOOLWRITE] = space->Shield[BOOLWRITE] - 128;
      if(Origine == 0) space->MyShootBall = -1;
      break;
    case 1:
      space->Shield[BOOLWRITE] = space->Shield[BOOLWRITE] - 64;
      if(Origine == 0) space->MyShootBall = -1;
      break;
    case 2:
      space->Shield[BOOLWRITE] = space->Shield[BOOLWRITE] - 32;
      if(Origine == 0) space->MyShootBall = -1;
      break;
    case 3:
      space->Shield[BOOLWRITE] = space->Shield[BOOLWRITE] - 16;
      if(Origine == 0) space->MyShootBall = -1;
      break;
    case 4:
      space->Shield[BOOLWRITE] = space->Shield[BOOLWRITE] - 8;
      if(Origine == 0) space->MyShootBall = -1;
      break;
    case 5:
      space->Shield[BOOLWRITE] = space->Shield[BOOLWRITE] - 4;
      if(Origine == 0) space->MyShootBall = -1;
      break;
    case 6:
      space->Shield[BOOLWRITE] = space->Shield[BOOLWRITE] - 2;
      if(Origine == 0) space->MyShootBall = -1;
      break;
    case 7:
      space->Shield[BOOLWRITE] = space->Shield[BOOLWRITE] - 1;
      if(Origine == 0) space->MyShootBall = -1;
      break;
    default:
      break;
  }
}

uint8_t MyShield(uint8_t x, uint8_t y, SPACE *space) {
  #define OFFSETXSHIELD -1
  if(y != 6) return 0x00;
  if((x >= 20 + OFFSETXSHIELD) && (x <= 27 + OFFSETXSHIELD)) {
    if(BOOLREAD(0, x - (20 + OFFSETXSHIELD), space)) return ShieldBlitz(0, x - (20 + OFFSETXSHIELD));
    else return 0x00;
  }
  if((x >= 28 + OFFSETXSHIELD) && (x <= 35 + OFFSETXSHIELD)) {
    if(BOOLREAD(1, x - (28 + OFFSETXSHIELD), space)) return ShieldBlitz(1, x - (28 + OFFSETXSHIELD));
    else return 0x00;
  }
  if((x >= 55 + OFFSETXSHIELD) && (x <= 62 + OFFSETXSHIELD)) {
    if(BOOLREAD(2, x - (55 + OFFSETXSHIELD), space)) return ShieldBlitz(0, x - (55 + OFFSETXSHIELD));
    else return 0x00;
  }
  if((x >= 63 + OFFSETXSHIELD) && (x <= 70 + OFFSETXSHIELD)) {
    if(BOOLREAD(3, x - (63 + OFFSETXSHIELD), space)) return ShieldBlitz(1, x - (63 + OFFSETXSHIELD));
    else return 0x00;
  }
  if((x >= 90 + OFFSETXSHIELD) && (x <= 97 + OFFSETXSHIELD)) {
    if(BOOLREAD(4, x - (90 + OFFSETXSHIELD), space)) return ShieldBlitz(0, x - (90 + OFFSETXSHIELD));
    else return 0x00;
  }
  if((x >= 98 + OFFSETXSHIELD) && (x <= 105 + OFFSETXSHIELD)) {
    if(BOOLREAD(5, x - (98 + OFFSETXSHIELD), space)) return ShieldBlitz(1, x - (98 + OFFSETXSHIELD));
    else return 0x00;
  }
  return 0x00;
}

uint8_t ShieldBlitz(uint8_t Part, uint8_t LineSH) {
  uint8_t Var0 = 0;
  switch(LineSH) {
    case 0: if(Part == 0) Var0 = 0b11110000; else Var0 = 0b00001111; break;
    case 1: if(Part == 0) Var0 = 0b11111100; else Var0 = 0b00001111; break;
    case 2:
    case 3:
    case 4:
    case 5: Var0 = 0b00001111; break;
    case 6: if(Part == 1) Var0 = 0b11111100; else Var0 = 0b00001111; break;
    case 7: if(Part == 1) Var0 = 0b11110000; else Var0 = 0b00001111; break;
    default: Var0 = 0b00000000; break;
  }
  return Var0;
}

uint8_t BOOLREAD(uint8_t SHnum, uint8_t LineSH, SPACE *space) {
  uint8_t Var0 = 0b10000000 >> LineSH;
  return((space->Shield[SHnum] & Var0) != 0);
}

void RemoveExplodOnMonsterGrid(SPACE *space) {
  uint8_t x, y;
  for(y=0; y<=3; y++) {
    for(x=0; x<=5; x++) {
      if(space->MonsterGrid[y][x] >= 11) space->MonsterGrid[y][x] = -1; 
      if(space->MonsterGrid[y][x] >= 8)  space->MonsterGrid[y][x] = space->MonsterGrid[y][x] + 1;
    }
  }
}

uint8_t background(uint8_t x, uint8_t y, SPACE *space) {
  uint8_t scr = space->ScrBackV + x;
  if(scr > 127) scr = space->ScrBackV + x - 128;
  return(0xff - back[y * 128 + scr]);
}

uint8_t Vesso(uint8_t x, uint8_t y, SPACE *space) {
  if((x - ShipPos >= 0) && (x - ShipPos < 13) && (y==7)) {
    if(ShipDead == 0) return vesso[x - ShipPos];
    else return vesso[x - ShipPos + (12 * space->oneFrame)];
  }
  return 0;
}

void UFO_Attack_Check(uint8_t x, SPACE *space) {
  if(space->MyShootBall == 0) {
    if((space->MyShootBallxpos >= space->UFOxPos) && (space->MyShootBallxpos <= space->UFOxPos + 14)) {
      for(x=1; x<100; x++) JOY_sound(x, 1);
      if(Live < 3) Live++;
      space->UFOxPos =- 120;
    }
  }
}

uint8_t MyShoot(uint8_t x, uint8_t y, SPACE *space) {
  if((space->MyShootBallxpos == x) && (y == space->MyShootBall)) {
    if(space->MyShootBall > -1) space->MyShootBallFrame = !space->MyShootBallFrame;
    else return 0x00;
    if(space->MyShootBallFrame == 1) space->MyShootBall--;
    Monster_Attack_Check(space);
    UFO_Attack_Check(x, space);
    return SHOOT[space->MyShootBallFrame];
  }
  return 0x00;
}

void Monster_Attack_Check(SPACE *space) {
  int8_t Varx = 0, Vary = 0;
  #define Xmouin   (space->MonsterGroupeXpos) 
  #define Ymouin   (space->MonsterGroupeYpos << 3) //-space->DecalageY8
  #define XPlus    (Xmouin + 84)
  #define YPlus    (Ymouin + (4*8))
  #define MYSHOOTX (space->MyShootBallxpos)
  #define MYSHOOTY ((space->MyShootBall << 3) + ((space->MyShootBallFrame + 1) << 2))
  if((MYSHOOTX >= Xmouin) && (MYSHOOTX <= XPlus) && (MYSHOOTY >= Ymouin) && (MYSHOOTY <= YPlus)) {
    //enter in the monster zone
    Vary = (MYSHOOTY - Ymouin + 4) >> 3;
    Varx = (MYSHOOTX - Xmouin + 7) / 14;
    if(Varx < 0) Varx = 0;
    if(Vary < 0) Vary = 0;
    if(Varx > 5) return;
    if(Vary > 3) return;
    if((space->MonsterGrid[Vary][Varx] > -1) && (space->MonsterGrid[Vary][Varx] < 6)) {
      JOY_sound(50, 10);
      space->MonsterGrid[Vary][Varx] = 8;
      space->MyShootBall = -1;
      SpeedControle(space);
    }
    //fin monster zone
  }
}

int8_t OuDansLaGrilleMonster(uint8_t x, uint8_t y, SPACE *space) {
  if(x < space->MonsterGroupeXpos) return -1;
  if(y < space->MonsterGroupeYpos) return -1;
  space->PositionDansGrilleMonsterX = (x - space->MonsterGroupeXpos) / 14;
  space->PositionDansGrilleMonsterY = (y - space->MonsterGroupeYpos);
  if(space->PositionDansGrilleMonsterX > 5) return -1;
  if(space->PositionDansGrilleMonsterY > 4) return -1;
  return 0;
}

uint8_t SplitSpriteDecalageY(uint8_t Input, uint8_t UPorDOWN, SPACE *space) {
  if(UPorDOWN) return(Input << space->DecalageY8);
  else return(Input >> (8 - space->DecalageY8));
}

uint8_t Murge_Split_UP_DOWN(uint8_t x, SPACE *space) {
  int8_t SpriteType = -1;
  int8_t ANIMs = -1;
  uint8_t Murge1 = 0;
  uint8_t Murge2 = 0;
  if(space->DecalageY8 == 0) {
    SpriteType = space->MonsterGrid[space->PositionDansGrilleMonsterY][space->PositionDansGrilleMonsterX];
    if(SpriteType < 8) ANIMs = space->anim * 14;
    else ANIMs = 0;
    if(SpriteType == -1) return 0x00;
    return Monsters[(WriteMonster14(x - space->MonsterGroupeXpos) + SpriteType * 14) + ANIMs];
  }
  else {
    //debut
    if(space->PositionDansGrilleMonsterY == 0) {
      SpriteType = space->MonsterGrid[space->PositionDansGrilleMonsterY][space->PositionDansGrilleMonsterX];
      if(SpriteType < 8) ANIMs = space->anim * 14;
      else ANIMs = 0;
      if(SpriteType != -1) Murge2 = SplitSpriteDecalageY(Monsters[(WriteMonster14(x - space->MonsterGroupeXpos) + SpriteType * 14) + ANIMs], 1, space);
      else Murge2 = 0x00;
      return Murge2;
    }
    else {
      SpriteType = space->MonsterGrid[space->PositionDansGrilleMonsterY - 1][space->PositionDansGrilleMonsterX];
      if(SpriteType < 8) ANIMs = space->anim * 14;
      else ANIMs = 0;
      if(SpriteType != -1) Murge1 = SplitSpriteDecalageY(Monsters[(WriteMonster14(x - space->MonsterGroupeXpos) + SpriteType * 14) + ANIMs], 0, space);
      else Murge1 = 0x00;
      SpriteType = space->MonsterGrid[space->PositionDansGrilleMonsterY][space->PositionDansGrilleMonsterX];
      if(SpriteType < 8) ANIMs = space->anim * 14;
      else ANIMs = 0;
      if(SpriteType != -1) Murge2 = SplitSpriteDecalageY(Monsters[(WriteMonster14(x - space->MonsterGroupeXpos) + SpriteType * 14) + ANIMs], 1, space);
      else Murge2 = 0x00;
      return(Murge1 | Murge2);
    }  
  } //fin
}

uint8_t WriteMonster14(uint8_t x) {
  while(x >= 14) x -= 14;
  return x;
}

uint8_t Monster(uint8_t x, uint8_t y, SPACE *space) {
  if(OuDansLaGrilleMonster(x, y, space) != -1) return  Murge_Split_UP_DOWN(x, space);
  return 0x00;
}

uint8_t MonsterRefreshMove(SPACE *space) {
  if(space->Direction == 1) {
    if(space->MonsterGroupeXpos < space->MonsterOffsetDroite) {
      space->MonsterGroupeXpos = space->MonsterGroupeXpos + 2;
      return 0;
    }
    else {
      if(space->DecalageY8 < 7) {
        space->DecalageY8 = space->DecalageY8 + 4;
        if(space->DecalageY8 > 7) space->DecalageY8 = 7; 
      }
      else {
        space->MonsterGroupeYpos++;
        space->DecalageY8 = 0;
      }
      space->Direction = 0;
      return 0;
    }
  }
  else {
    if(space->MonsterGroupeXpos > space->MonsterOffsetGauche) {
      space->MonsterGroupeXpos = space->MonsterGroupeXpos - 2;
      return 0;
    }
    else {
      if(space->DecalageY8 < 7) {
        space->DecalageY8 = space->DecalageY8 + 4;
        if(space->DecalageY8 > 7) space->DecalageY8 = 7;
      }
      else {
        space->MonsterGroupeYpos++;
        space->DecalageY8 = 0;
      }
      space->Direction = 1;
      return 0;
    }
  }
}

void VarResetNewLevel(SPACE *space) {
  ShieldRemoved = 0;
  SpeedShootMonster = 0;
  MONSTERrest = 24;
  LoadMonstersLevels(LEVELS, space);
  space->Shield[0] = 255;
  space->Shield[1] = 255;
  space->Shield[2] = 255;
  space->Shield[3] = 255;
  space->Shield[4] = 255;
  space->Shield[5] = 255;
  space->MonsterShoot[0] = 16;
  space->MonsterShoot[1] = 16;
  space->UFOxPos = -120;

  space->MyShootBall = -1;
  space->MyShootBallxpos = 0;
  space->MyShootBallFrame = 0;
  space->anim = 0;
  space->frame = 0;
  space->PositionDansGrilleMonsterX = 0;
  space->PositionDansGrilleMonsterY = 0;
  space->MonsterFloorMax = 3;
  space->MonsterOffsetGauche = 0;
  space->MonsterOffsetDroite = 44;
  space->MonsterGroupeXpos = 20;
  if(LEVELS > 3) space->MonsterGroupeYpos = 1;
  else space->MonsterGroupeYpos = 0;
  space->DecalageY8 = 0;
  space->frameMax = 8;
  space->Direction = 1; //1 right 0 gauche
  space->oneFrame = 0;
}
```



GAMES
=
There are many games but i got stucked with the tiny invaders that was my childhood favourite game 
-

Tiny Invaders
-




