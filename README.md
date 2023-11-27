# RNBIP_Simulations
idk what I am doin but it is funn hehehehehe

## Installation of RNBIP
- Download and run rnbip to use the files
### Setup Instructions Windows
  - Download and Install [Python3](https://www.python.org/downloads/)
  - Open CommandPrompt or Windows Powershell

You can Install the rnbip with the following command.
```bash
pip3 install rnbip
```
![](/docs/test.gif)

### Launch RNBIP
```bash
python3 -m rnbip_emulator
```
![](/docs/test2.gif)
### Setup Instructions Linux
Use your favourite package manager to install python3 and python-pip.   
Install the rnbip with the following command.
```bash
pip3 install rnbip
```
### Launch RNBIP
```bash
python3 -m rnbip_emulator
```
Alternatively, if installed scripts are added to path by default
```bash
rnbip
```


# Now that everything is installed and working, you can copy paste the .asm files _without_ comments

## Now to understand how it works :
- So basically you run an assembly code in the editor which is on the top right section, this is your IDE basically.
- Next you compile the code, keep in mind this thing doesn't work with comments of asm like ;, so be sure to remove them if you get compiler error.
- Now it works just like how gdb works with C, it changes the color of the data lines to demostrate what is happening on each clock cycle. 
- **Instruction** - this shows which command is going on.
- **OpCode** - this shows the operation code (given in the pdf for each instruction)
- **PC** - VERY IMP if you want to write loops, it shows where the PC is pointing to so when you write loops using Jumps you have to mention the address of line which shows in PC not in your code.
- **Register Array** - this shows what is stored in each array in hexadecimal system.
- Next clock cycle , reset, run 10 cycles, do exactly what they say.

### Add 2 Numbers 
-  **CLR:** Clear all registers and the carry flag.
- **MVI R1 0A:** Load immediate value 0A (10 in decimal) into register R1.
- **MVI R2 05:** Load immediate value 05 (5 in decimal) into register R2.
- **MVS R1:** Move the contents of register R1 to the stack pointer.
- **ADA R2:** Add the contents of register R2 to the accumulator (R0).
- **MVD R3:** Move the contents of the accumulator (R0) to register R3.

### Loop till Carry
- **CLR:** Clear all registers and the carry flag.
- **MVI R6 B1:** Load immediate value B1 (hexadecimal) into register R6.
- **MVI R7 0F:** Load immediate value 0F (15 in decimal) into register R7.
- **MVS R6:** Move the contents of register R6 to the stack pointer.
- **ADA R7:** Add the contents of register R7 to the accumulator (R0).
- **JCD C 00:** Jump to address 00 if the carry flag is set.
- **JUD 06:** Jump to address 06 unconditionally.

### Multiply 2 Numbers
- **CLR:** Clear all registers and the carry flag.
- **MVI R1 05:** Load immediate value 05 into register R1.
- **MVI R2 03:** Load immediate value 03 into register R2.
- **ADA R1:** Add the contents of register R1 to the accumulator (R0).
- **MVD R3:** Move the contents of the accumulator (R0) to register R3.
- **DCR R2:** Decrement the contents of register R2.
- **JUD 06:** Jump to address 06 unconditionally.


### Fibbonaci 
- **CLR:** Clear all registers and the carry flag.
- **MVI R1 00:** Load immediate value 00 into register 1 as we are basically storing the n-2th term here.
- **MVI R2 01:** Load immediate value 01 into register 2 as 1 because we are storing n-1th term here.
- **MVI R3 04:** This is basically the n for the term you want to find.
- **MVS R2:** We are storing n-1th term to R0.
- **ADA R1:** We are adding n-2th term to R0.
- Now here is the beauty.
- **MVD R2:** Now the current term becomes n-1th term so storing R0 into R2.
- **SCA R1:** doing this we will get as R0= R1+R2, now it becomes R1+R2-R1 becoming the n-1th term but technically n-2th term for the next permutation and this is the beauty.
-**MVD R1:** now storing that n-2th term to our original n-2th term storage.
- **DCR R3:** Decrementing R3 after one permutation.
- **JUD 08:** Jumping to 0x08 which is MVS R2 to run this program in loop.
