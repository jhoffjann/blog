---
id: 1196
title: Get OpenCV up and running with IntelliJ and Mac OS X
date: 2014-10-20T16:43:23+00:00
author: Jannik
layout: post
guid: http://aufeinwort.org/?p=1196
permalink: /2014/10/get-opencv-up-and-running-with-intellij-and-mac-os-x/
categories:
  - Coding
---
Edit 4.11.2014: Updated for OpenCV 2.4.10

The last weeks I spent a lot of time to get OpenCV up and running with IntelliJ. I will use the OpenCV library for my Bachelor Thesis so it was somehow really important for me to test the possibilities of this library together with Java.

I learned early that it is not too easy to get it working the right way. Library not found and Compiling errors have been my mates for the whole way.

So for everyone who finds this and for myself in the future I documented how it is done right.

Prerequisites: Java, Ant, Python, cmake (I highly recommend to install all of those with Homebrew)

Open the terminal and switch to your working directory.

Clone the Git-Repository:
  
`git clone git://github.com/Itseez/opencv.git`

Switch to the folder and get the latest working version.
  
`cd opencv</p>
<p>git checkout 2.4.10</p>
<p>mkdir build</p>
<p>cd build<br />
` 
  
Create your C++ Compiling files
  
`cmake -DBUILD_SHARED_LIBS=OFF ..`

Compile the whole thing
  
`sudo make -j8</p>
<p>sudo make install`

Now open IntelliJ and go right to the project where you want to use OpenCV.

Go to File > Project Structure and add the created opencv-2410.jar located at `opencv/build/bin/` as a module.

After applying go to Run > Debug Configurations and insert
  
`-Djava.library.path=<path to your buildfolder>/opencv/build/lib`

And finally, you are done. Now you can just import the libraries classes via org.opencv&#8230;

Hope this will help at least a few people.