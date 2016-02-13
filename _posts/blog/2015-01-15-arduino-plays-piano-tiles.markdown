---
layout: post
title: "Arduino Plays Piano Tiles"
date: 2015-01-15 18:00:00
author: Nikhilendra Gudisa
categories:
- blog
- android-games
- Matlab
- ADB tool
img: 
thumb: default_thumb.png
---

Ever wondered if your phone can play games by itself. Yes, it is possible. You can build a circuit to play Piano tiles on your smartphone.

&nbsp;

<a href="http://themotivatedengineer.com/blog/wp-content/uploads/2015/01/IMG_15672.jpg"><img class="  wp-image-49 aligncenter" src="http://themotivatedengineer.com/blog/wp-content/uploads/2015/01/IMG_15672-300x224.jpg" alt="IMG_1567" width="366" height="273" /></a>

&nbsp;

And the circuit can be built with simple components like <strong><em>Light sensors, Relays and Arduino.</em></strong><a href="http://themotivatedengineer.com/blog/wp-content/uploads/2015/01/Slide1.png"><img class="  wp-image-28 aligncenter" src="http://themotivatedengineer.com/blog/wp-content/uploads/2015/01/Slide1-300x169.png" alt="Slide1" width="397" height="224" /></a>

&nbsp;

<strong>Three main functions of the circuit are :</strong>
<ol>
	<li>Sensing color of the tile (Black or White)</li>
	<li>Processing the color information and generating timing  for the touch (Arduino)</li>
	<li>Simulating capacitive touch (Relays)</li>
</ol>
&nbsp;

<a href="http://themotivatedengineer.com/blog/wp-content/uploads/2015/01/Piano-tiles-New-Page-1.png"><img class="  wp-image-37 aligncenter" src="http://themotivatedengineer.com/blog/wp-content/uploads/2015/01/Piano-tiles-New-Page-1-300x70.png" alt="Piano tiles - New Page (1)" width="424" height="99" /></a>

&nbsp;

<b>Building the circuit:</b>

<strong>Sensing:</strong>
We use light dependent resistors (LDRs) to sense if the tiles are white or black.  Four LDRs are positioned over the screen each facing one tile. The LDRs have been connected to the back of the cardboard like this.

<a href="http://themotivatedengineer.com/blog/wp-content/uploads/2015/01/Untitled3.png"><img class="  wp-image-43 aligncenter" src="http://themotivatedengineer.com/blog/wp-content/uploads/2015/01/Untitled3-300x198.png" alt="Untitled3" width="367" height="242" /></a>

The LDR resistance changes with the intensity of Light. Higher the intensity of light, lesser the resistance. LDR is placed in a Voltage divider circuit to produce a voltage proportional to its resistance.The LDRs are connected to the analog input pins of the Arduino as shown.

<a href="http://themotivatedengineer.com/blog/wp-content/uploads/2015/01/Untitled4.png"><img class="  wp-image-44 aligncenter" src="http://themotivatedengineer.com/blog/wp-content/uploads/2015/01/Untitled4-300x278.png" alt="Untitled4" width="362" height="336" /></a>

Practically, this is how you would connect the circuit. You can check the <a href="https://github.com/psurya1994/arduino-plays-piano-tiles/blob/master/Code/test_ldr/test_ldr.ino"><b>test_ldr </b></a>code  to see if the LDRs are working fine. When you run the code, you will get a high value from the LDR if it’s sensing black, else you get a low value.

<strong><strong>Processing:
</strong></strong>Arduino reads the voltage drop across the LDR. Observe the voltage voltages for Black and White tiles, choose a suitable threshold voltage say Vt. If  (V&lt;Vt) larger the drop across LDR, larger the resistance, which implies a Black tile and vice versa. If found tile is a Black one simulate touch corresponding to that tile.

<a href="http://themotivatedengineer.com/blog/wp-content/uploads/2015/01/LDR-ScreenShot3.png"><img class="  wp-image-51 aligncenter" src="http://themotivatedengineer.com/blog/wp-content/uploads/2015/01/LDR-ScreenShot3-287x300.png" alt="LDR ScreenShot3" width="359" height="375" /></a>

<b>Touching:</b>

For this we have to understand how capacitive touch screens work. The electrodes apply a low voltage to the conductive layer creating a uniform electrostatic field. When a finger hits the screen a tiny electrical charge is transferred to the finger to complete the circuit creating a voltage drop at that point on the screen. The location of this voltage drop is recorded by the controller and this is how a capacitive touch screen works.

<strong><strong><a href="http://themotivatedengineer.com/blog/wp-content/uploads/2015/01/Untitled2.png"><img class="  wp-image-40 aligncenter" src="http://themotivatedengineer.com/blog/wp-content/uploads/2015/01/Untitled2-300x184.png" alt="Untitled2" width="351" height="215" /></a></strong></strong>

We are going to use this concept, except that in the place of a finger, we use the ground pin on the arduino to transfer the charge on the screen. To have more surface area on the display of the screen, we use a coin.

Relays are directly connected to the output pin of the Arduino. It is equivalent to a touch if the voltage given is high as there is a path for the current to flow to the ground. It is equivalent to not touching if the voltage given is low.

<a href="http://themotivatedengineer.com/blog/wp-content/uploads/2015/01/Slide2.png"><img class="alignnone size-medium wp-image-41" src="http://themotivatedengineer.com/blog/wp-content/uploads/2015/01/Slide2-300x169.png" alt="Slide2" width="300" height="169" /></a> <a href="http://themotivatedengineer.com/blog/wp-content/uploads/2015/01/Slide3.png"><img class="alignnone size-medium wp-image-42" src="http://themotivatedengineer.com/blog/wp-content/uploads/2015/01/Slide3-300x169.png" alt="Slide3" width="300" height="169" /></a>

Run the <a href="https://github.com/psurya1994/arduino-plays-piano-tiles/blob/master/Code/test_touch/test_touch.ino"><b>test_relay </b></a>code at this link to see if the electronic touch is simulated properly.

<strong>Finishing Touch:</strong>

Once you the connect the circuit and dump the code <a href="https://github.com/psurya1994/arduino-plays-piano-tiles/blob/master/Code/main/main.ino"><b>main.ino </b></a>at this link, your circuit should start working. If not, it is because the delays are not adjusted perfectly. Tweak the delay values in the code and it should work.

And you built a circuit that can play Piano Tiles better than any human in the world!!

<strong>Source code and Schematics:</strong>

<a href="https://github.com/psurya1994/arduino-plays-piano-tiles">https://github.com/psurya1994/arduino-plays-piano-tiles</a>

<strong>Tutorial on Youtube:</strong>

[embed]https://www.youtube.com/watch?v=8hlQ0MiowN8&#038;src_vid=2TJ7itil1cc[/embed]

&nbsp;

<strong>Demonstration of the project:
</strong>

[embed]https://www.youtube.com/watch?v=2TJ7itil1cc[/embed]

<strong> </strong>

&nbsp;