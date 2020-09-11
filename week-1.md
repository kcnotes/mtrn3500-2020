---
layout: page
title: Week 1
permalink: /week-1/
---

# Week 1
Welcome to MTRN3500! 

## Galil Controllers
* We use a RIO controller in the labs, this is a programmable logic controller (PLC). 
	* You can think of a PLC as a high level microcontroller (e.g. Arduino), but with various things integrated within, including memory, interfaces (like Ethernet), I/O modules and control modules like PID. 

<!-- <img src="http://www.galilmc.com/sites/default/files/styles/product_page_image/public/products/rio-471xx_big.png" style="width:300px;"/> -->
* For the one in the lab:
	* You can produce and read analog and digital voltages
	* There is a set of LEDs at the top of the board, which you can write to
	* You'll notice there is an ethernet port - the board is connected via Ethernet to your lab computer
	* One of the analog outputs are connected to a motor
	* There is an encoder connected to that motor
	* There are programmable PID control loops. Some of you may have learnt about PID, some not - these are basically three parameters you can tweak to perform things like automatically changing the temperature of a room, or make the motor go to a specific position without overshooting.

## Running code
We send ASCII commands via Ethernet to read and write to the Galil controller. Connecting and sending the commands will be abstracted out for you in the first assignment - but for the second assignment, you will need to write your own. The actual ASCII commands you have to send are defined in the **RIO Firmware Command Reference**, in Moodle.

<div class="code-example" markdown="1" style="border-left:8px solid #41d693;">
Whenever something isn't doing what you think it should be doing, always check the documentation!
</div>

To see the actual controller, open up the Camera app in the remote desktop. Also open up GalilTools, which is one way of sending these commands.

* On the right toolbar, there is a terminal. It should say that the controller is connected via a specific IP address.
* You can type commands in this terminal.

<div class="code-example" markdown="1">
Type the following. `OP` stands for output port. There are two banks of LEDs, each bank has 8 LEDs. See page 137 of the Galil Command Reference.
</div>
```
'Example, this is a comment
OP 0,0
OP 1,0
```