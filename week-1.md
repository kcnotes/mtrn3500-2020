---
layout: page
title: Week 1
permalink: /week-1/
---

# Galil Controllers
* We use a RIO controller in the labs, this is a programmable logic controller (PLC). 
	* You can think of a PLC as a high level microcontroller (e.g. Arduino), but with various things integrated within, including memory, interfaces (like Ethernet), I/O modules and control modules like PID. 

<img src="http://www.galilmc.com/sites/default/files/styles/product_page_image/public/products/rio-47200_big_2.png" style="width:300px;"/>
* In the labs, (I believe) we have the RIO-4720x, which has a bunch of things. 
	* You can produce and read analog and digital voltages
	* There is a set of LEDs at the top of the board, which you can write to
	* These are accessible through groups of screw-terminal points, labelled as 'banks'
	* You'll notice there is an ethernet port - it is connected via Ethernet to your lab computer
	* There are programmable PID control loops. Some of you may have learnt about PID, some not - these are basically three parameters you can tweak to perform things like automatically changing the temperature of a room, or keeping a wheel spinning at a certain RPM.

# Running code
We send ASCII commands via Ethernet to read and write to the Galil controller. Connecting and sending the commands will be abstracted out for you in the first assignment - but for the second assignment, you will need to write your own. The actual ASCII commands you have to send are defined in the **RIO Firmware Command Reference**, in Moodle.

<div class="code-example" markdown="1" style="border-left:8px solid #41d693;">
Whenever something isn't doing what you think it should be doing, always check the documentation!
</div>

GalilTools is one way of sending these commands