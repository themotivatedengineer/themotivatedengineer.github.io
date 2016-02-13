---
layout: post
title: "Arduino Plays Stick Hero"
date: 2015-01-18 18:00:00
author: Sharan Erukulla
categories:
- blog
- android-games
- Matlab
- ADB tool
img: 
thumb: default_thumb.png
---
Are you a gaming freak? Want to top the high score list? If your answer is yes you are at the right place. Can all this be achieved with you sitting idle and your phone doing all the talking? Yes it can be done and we'll show you how. 


<div style="text-align:center" markdown="1">![Stick hero 1](/assets/img/blog/stick-1.jpg) 

</div>

**Introduction to _Stick Hero_:** 
Stick hero is one of the world famous, time eating game with over 10 Million Downloads. To download the App on your smart phone click [here](https://play.google.com/store/apps/details?id=com.ketchapp.stickhero&hl=en). If you are new to the game, have a look at the game play [here](https://www.youtube.com/watch?v=E97BeH6WYlo). 

**Components Required:**

<div style="text-align:center" markdown="1">![Stick hero 2](/assets/img/blog/stick-2.png) 

</div>
_Single Strand Wires, Coins, Relays_ are used to simulate the touch on the capacitive touch screen of phones and tablets. _Arduino_ is used to control the duration of the touch. Tripod, for holding a phone above the camera (refer fig-1) 


**Software's**** Required:** 

[_Matlab_](http://in.mathworks.com/downloads/web_downloads): Used for Image Processing. 

[_Arduino IDE_](https://www.arduino.cc/en/main/software): For programming the Arduino.

[IP Cam](https://play.google.com/store/apps/details?id=com.pas.webcam&hl=en): It is an android app which enables us to use our smartphones cam as a web cam. This project involves three basic steps,

1.  Detect the black pillars
2.  Determine the amount of time the screen is to be touched
3.  Simulate touch on the tablet/phone[![Blank Flowchart - New Page](http://themotivatedengineer.com/blog/wp-content/uploads/2015/01/Blank-Flowchart-New-Page.png)](http://themotivatedengineer.com/blog/wp-content/uploads/2015/01/Blank-Flowchart-New-Page.png)

  **Detecting the black pillars:** 

This is done by using Matlab. The image that is captured from the IP Cam is  processed and the locations of the black pillars are determined. The distance between the black pillars is calculated and the corresponding data is sent to the Arduino through serial communication. The source code for the above processing can be found [here](https://github.com/psurya1994/arduino-plays-stick-hero/tree/master/Code/MATLAB). 

**Determining the duration of the touch:** 

Based on the data arrived from Matlab, the duration of the touch is adjusted such that the stick exactly falls on the adjacent pillar. The source code for the arduino can be found [here](https://github.com/psurya1994/arduino-plays-stick-hero/tree/master/Code/Arduino). 

**Simulating Touch:** 

For this we have to understand how capacitive touch screens work. The electrodes apply a low voltage to the conductive layer creating a uniform electrostatic field. When a finger hits the screen a tiny electrical charge is transferred to the finger to complete the circuit creating a voltage drop at that point on the screen. The location of this voltage drop is recorded by the controller and this is how a capacitive touch screen works. 

****[![Untitled2](http://themotivatedengineer.com/blog/wp-content/uploads/2015/01/Untitled2-300x184.png)](http://themotivatedengineer.com/blog/wp-content/uploads/2015/01/Untitled2.png)**** 

We are going to use this concept, except that in the place of a finger, we use the ground pin on the arduino to transfer the charge on the screen. To have more surface area on the display of the screen, we use a coin. Relays are directly connected to the output pin of the Arduino. It is equivalent to a touch if the voltage given is high as there is a path for the current to flow to the ground. It is equivalent to not touching if the voltage given is low. 

[![Slide2](http://themotivatedengineer.com/blog/wp-content/uploads/2015/01/Slide2-300x169.png)](http://themotivatedengineer.com/blog/wp-content/uploads/2015/01/Slide2.png)[![Slide3](http://themotivatedengineer.com/blog/wp-content/uploads/2015/01/Slide3-300x169.png)](http://themotivatedengineer.com/blog/wp-content/uploads/2015/01/Slide3.png)

Run the [**test_relay** ](https://github.com/psurya1994/arduino-plays-piano-tiles/blob/master/Code/test_touch/test_touch.ino)code at this link to see if the electronic touch is simulated properly. If you pass the above three tests, you are all set to break the records! :D 

**Source Code and Schematics:** This is an open source project, the code and schematics can be found in the below link: 
[https://github.com/psurya1994/arduino-plays-stick-hero](https://github.com/psurya1994/arduino-plays-stick-hero) 

**Project Demostration:** 

<iframe width="560" height="315" src="https://www.youtube.com/embed/dJW59UliLhc" frameborder="0" allowfullscreen></iframe>