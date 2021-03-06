# py10x-engine

## What is this?
This is is a programming language based on Olivetti Programma's Assembly.
This is **not** an emulator. Emulators are another thing, this language coniugates the agility of Programma's Assembly with the strongs of today's PCs.

## Language
### Overview
In this language all the basic operation are made n the A register, the "accumulator". 
Store register are: B, C, D, E, F.
Working register are: M, A, R

The store register may be splitted and the splitted part is wrote with a / afer the register name. For example E/ in E splitted.
A splitted register must be write with a space after the /

Every operation is made on the A register so if you read:
B-
You're making
A-B

Math operation are usable also on other register.

#### K register
There are 100 (0-99) register that may be directly addressed with the K and the number. They work as normal register.

### Order
You must write every symbolic function with first the register and last the operation. In advanced math operation you can use both "sin A" and "A sin", as you prefer.

### Basic functions
The mathematic fundamental operations are:
* +, that make A = A + X
* -, that make A = A - X
* x, that make A = A * X
* :, that make A = A / X, also saves in R the rest of division
* sqrt, that make sqrt X, also saves in M 2(sqrt(X))
* /x, that make the M percentage of A
* /:, that make the division
* S, take a number and puts it in M
* /+ and /-, that make X = X+-1
* pi, that saves the pi (π) value in the given register, also the Greek symbol works

### Print
There are two instructions related to printing:
* The # prints the value of the given register
* The /# writes a blank line
### Register functions
Registers are like variables. Operation are beetween the main register (A and M) and a given register. Differently from Programma 101 the M register is not implied where there is no register in the command.
* The >< exchanges the A register with the given register. 
* The ! puts M in the given register
* The ^ puts the given register in A

#### Operations on A
* A>< puts the abs(A) in A
* /^ deletes decimal part of A
* />< puts the decimal part of A in M

### Math
Math functions are ispired by Olivetti P652 and are:
* sin: Sine
* cos: Cosine
* * tan: Tangent

### Shell commands
There are some shell commands:
* RESET: Reset the system
* EXIT: Close the program
* PRINT: Print the magnetic carg

### Constant
Constants are numbers definied in the virtual magnetic card with this syntax:

cnst X number

So, if you want to store in D the p value you should write:

cnst D 3.14

### Jumps
Jumps are quite different from P101 in labels but not in functions.

#### IF
An If jump is identified by a "Ws" plus a number label and its start point by "W" and the same number.

IF jumps when the number in A is > 0. If you need another condition you may modify A with the equation rules (for esample if "A > 5 => A -5 > 0)

If can't be used for starting programs.
#### GOTO
A GOTO jump is identifiec by a "Vs" plus a number label and its start point by "V" and the same number.

A GOTO is used for starting programs in "memload" loading and jumps everytime, without consideration for the variables.

### Comments
A comment in a row starts with "|". Comment are shown in debug mode and supported only in "memload"

### Magnetic card
Magnetic card is a file with commands written in.

You can open a magnetic card with three commands:

* memload: Like real P101 saves the program in memory and expect for a "V"+ number instruction for start the program in that point
* open: open the program and runs it sequentially
* oldopen: Compatibility mode, does not support jumps

## Debug mode
In debug mode are shown comment and the register content step-by-step. It's opened with the shell parameter "debug"

## Differences beetween P101 and this
* P101 has the RS command that exchanges R and D in magnetic cards introduction because MC introduction deletes D-F registers. In this emulator there is no this deletion so there is no RS

## Functions
### Done
* Basic functions
* Print functions
* Math functions
* Jumps
* Constant
### Working on it
* Realistic system for string in memory
* Plotting
* Jumps and condition like P652
* Register system with laberls for P652
* Direct loading from OS shell
* Recursion in Memload
* /! for change the sigm
* Exp (e^x) and /exp (a^m)
* Arc 
* /^ (puts X in M)
* Jumps labels like P652 (L and J)
### Information needed
* Constant like P101
