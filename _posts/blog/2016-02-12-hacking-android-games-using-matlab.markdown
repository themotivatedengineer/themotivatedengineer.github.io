---
layout: post
title: "Hacking Android games using MATLAB [without root]"
date: 2016-02-12 18:00:00
author: Sandeep Nadella
categories:
- blog
- android-games
- Matlab
- ADB tool
img: hacking-android-mobile-game-matlab.png
thumb: default_thumb.png
---
Have you ever wondered if you can do some image processing stuff on a game and automate it to make a high score? This post discusses how to hack android games using image processing in Matlab.

We will be hacking two games:

*   [Stick Hero](https://play.google.com/store/apps/details?id=com.ketchapp.stickhero&hl=en "stick hero play store link")
*   [Draw a box](https://play.google.com/store/apps/details?id=com.Armsta.DrawABox&hl=en "draw a box play store link")

You need not be a pro Matlab user for this. Just having Matlab installed and having an Android phone alone is enough. I'm currently using Matlab in Windows but you can even try out Matlab in Linux or [Scilab](http://www.scilab.org/ "scilab site link") for this. The commands might differ if you are using Scilab. The Android test device that I will be using is the OnePlus One. It has a resolution of 1080X1920(On screen buttons turned off). So the pixel location that  I'll be using may vary depending on the device you are using. I will tell you how to determine these locations for your device. This method works on all Android devices including Android Wear.  So without any delay lets get started.

* * *

### **Components required:**

*   Android Device
*   USB cable
*   PC or Mac with [Matlab](http://in.mathworks.com/products/matlab/ "matlab site link") with [Image Processing Toolbox](http://in.mathworks.com/products/image/index.html?s_cid=BB "Image Processing Toolbox link")

* * *

### **Step 1: Enabling developer options and installing drivers**

Go to Settings->About phone. Scroll down to Build number and tap it 5-6 times until it says developer options are enabled. Now download the ADB device drivers for your device. You can get these drivers from [Universal drivers](http://adbdriver.com/downloads/ "universal adb drivers") or [developer.android.com](http://developer.android.com/tools/extras/oem-usb.html#InstallingDriver "usb adb drivers"). If these don't work then you can google the term "ADB drivers for ________" and download the drivers suitable for your device from XDA developers forum. Check in Device Manager if the installation was successful. You will notice Android ADB device when connected. Now download the zip file containing the adb file and Matlab scripts from here [StickHero_DrawABox_Hack](http://themotivatedengineer.com/blog/wp-content/uploads/2015/01/StickHero_DrawABox_Hack.zip).

**Note:** This check is not required if you are confident that the drivers are installed properly. Open command prompt and navigate to the directory of the extracted game folder containing adb.exe file. The command is "cd dir_name" to change folders in Windows and Linux. "ls" to view contents of current directory. From this directory type "adb devices". Your device name must be displayed else drivers are not installed properly if so reinstall from a different source. If installed properly depending on the Android version running a prompt may pop up on the device containing RSA fingerprint key. Check the option "Always allow" and confirm.

* * *

### **Step 2: Setting up Matlab**

Make sure Matlab being installed has Image Processing Toolbox. This [post](http://stackoverflow.com/questions/2060382/how-would-one-check-for-installed-matlab-toolboxes-in-a-script-function) might help. Open Matlab and set its current working directory to the game folder extracted.

* * *

### **Step 3: Running the script and understanding it**

Make sure your current working directory points to the game folder that you are going to hack. Open the game in your device and click play. Then run the matlab script file(.m file). The code is written keeping in mind of people who are new to programming. The code is well commented. Lot of optimization of code is possible which is neglected for convenience. "<span style="color: #ff9900;">Test.m</span>" file contains the code for capturing a single screenshot and determining the pixel locations for your device. Run this code after clicking play and use data cursor to determine the pixel locations.


Note: For running the script <span style="color: #ff9900;">stickherowithfruits.m</span> you need to copy <span style="color: #ff9900;">sendevent_input.sh</span> file to /sdcard/ of your device. This method is not reliable to achieve high scores. Use stickhero.m for achieving high scores.(Higher than the scores that can be achieved by using [Arduino](http://www.arduino.cc/ "arduino site link") mentioned [here](http://themotivatedengineer.com/blog/project-arduino-plays-stick-hero/ "Project – Arduino Plays Stick Hero") :p :)).

* * *

### Stick Hero Gallery:

* * *

### Draw A Box Gallery:


* * *

### GitHub links for the project:

*   [Stick Hero](https://github.com/AndroSanDev/Stick-Hero-Hack "github link to androsandev ")
*   [Draw A Box](https://github.com/AndroSanDev/Draw-A-Box-Hack "link to github androsandev draw a box")

* * *

### Video demonstration of the projects:

<iframe width="560" height="315" src="https://www.youtube.com/embed/BQ5oVjFxYY4" frameborder="0" allowfullscreen></iframe>
<iframe width="560" height="315" src="https://www.youtube.com/embed/_WbKYmGN9eQ" frameborder="0" allowfullscreen></iframe>

* * *

* * *