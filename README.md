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


## Now that everything is installed and working, you can copy paste the .asm files _without_ comments

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


