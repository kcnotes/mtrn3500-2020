---
layout: page
title: Week 1
permalink: /week-1/
---

# Week 1
Welcome to MTRN3500! 

## Galil Controllers
* We use a RIO controller in the labs, this is a programmable logic controller (PLC). 
	* You can think of a PLC as a high level microcontroller (e.g. Arduino), but with various things integrated within, including memory, interfaces (like Ethernet), I/O modules and control modules like PID. It's used to control and interface with larger robotics systems with various modules/components. An example of a system would be an Amazon delivery warehouse with conveyors, light sensors, barcodes - a PLC can operate and both send conveyor movements and receive sensor data.

<img src="/mtrn3500-2020/rio.png" style="width:300px;"/>
* For the one in the lab:
	* You can produce and read analog and digital voltages
	* There are two banks of LEDs at the top of the board, which you can write to
	* You'll notice there is an ethernet cable - the board is connected via Ethernet to your lab computer
	* One of the analog outputs are connected to a motor
	* There is an encoder connected to that motor
	* There are programmable PID control loops. Some of you may have learnt about PID, some not - these are basically three parameters you can tweak to perform things like automatically changing the temperature of a room, or make the motor go to a specific position without overshooting.

<img src="/mtrn3500-2020/ass1setup.png" />

## Running code
We send ASCII commands via Ethernet to read and write to the Galil controller. Connecting and sending the commands will be abstracted out for you in the first assignment - but for the second assignment, you will need to write your own. The actual ASCII commands you have to send are defined in the **RIO Firmware Command Reference**, in Moodle.

## Tasks to do
* Set up your Visual Studio project by following the **Assignment 1 guide under Week 5** in Moodle.
* Try send commands to the RIO, if this is set up by today.
* Start working on the assignment.

<div class="code-example" markdown="1" style="border-left:8px solid #41d693;">
Whenever something isn't doing what you think it should be doing, always check the documentation!
</div>

To see the actual controller, open up the Camera app in the remote desktop. Also open up GalilTools, which is one way of sending these commands.

* On the right toolbar, there is a terminal. It should say that the controller is connected via a specific IP address.
* You can type commands in this terminal.
* On the top bar, go to Controller > Connect - this gives you a list of connected computers. Ethernet is set - you'll see the address. Normally you'd hit Connect, but this is already done for you. 
* Top two banks of LEDs (a bank is a set of 8 LEDs here) are the digital outputs.
* The bottom left bank (the 'low' bank) is fed back into the digital input, which lets us test input commands.

<div class="code-example" markdown="1">
Type the following. `OP` stands for output port. See page 137 of the Galil Command Reference. 
</div>
```
OP 0,0;
OP 1,0;
```

<div class="code-example" markdown="1">
The analog output, channel 7, is connected to the motor. Try the following:
</div>
```
AO 7,1;
AO 7,2;
AO 7,0;
```