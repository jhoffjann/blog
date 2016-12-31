---
layout: post
status: publish
published: true
title: Get OpenCV up and running with IntelliJ and Mac OS X
author:
  display_name: Jannik
  login: Jannik
  email: mail@aufeinwort.org
  url: ''
author_login: Jannik
author_email: mail@aufeinwort.org
wordpress_id: 1196
wordpress_url: http://aufeinwort.org/?p=1196
date: '2014-10-20 16:43:23 +0200'
date_gmt: '2014-10-20 14:43:23 +0200'
categories:
- Coding
tags: []
comments:
- id: 4300
  author: Kubra
  author_email: ce.kubra@gmail.com
  author_url: ''
  date: '2015-03-18 14:09:09 +0100'
  date_gmt: '2015-03-18 13:09:09 +0100'
  content: "Hi,\r\n\r\nFirstly thank you because this sharing is newest for openCV
    for IntelliJ, but I had a problem. After \"sudo make install\" I had no opencv-2410.jar.
    What can be the problem with it ?\r\n\r\nThanks again."
- id: 4301
  author: Jannik
  author_email: mail@aufeinwort.org
  author_url: ''
  date: '2015-03-18 14:54:23 +0100'
  date_gmt: '2015-03-18 13:54:23 +0100'
  content: "Hi Kubra,\r\n\r\nGlad this helped you. I had the same problem at first.
    Please check again you have all the prerequisites (Java, Ant, Python, cmake) installed.
    OpenCV is using all of them during the Compilation process to build the packages.\r\n\r\nGood
    Luck."
- id: 4696
  author: Victor
  author_email: vdgp@yahoo.com
  author_url: ''
  date: '2015-09-13 20:34:09 +0200'
  date_gmt: '2015-09-13 19:34:09 +0200'
  content: "Hi, \r\n\r\n\r\nI recomend, verify if you have installed ant and its JAVA_HOME
    variable is set correctly."
- id: 45767
  author: Asinus_Rex
  author_email: elburro94@yahoo.es
  author_url: ''
  date: '2016-01-08 21:10:56 +0100'
  date_gmt: '2016-01-08 20:10:56 +0100'
  content: There is an issue with this version of opencv on Yosemite, try a newer
    version of the library.
---
<p>Edit 4.11.2014: Updated for OpenCV 2.4.10</p>
<p>The last weeks I spent a lot of time to get OpenCV up and running with IntelliJ. I will use the OpenCV library for my Bachelor Thesis so it was somehow really important for me to test the possibilities of this library together with Java.</p>
<p>I learned early that it is not too easy to get it working the right way. Library not found and Compiling errors have been my mates for the whole way.</p>
<p>So for everyone who finds this and for myself in the future I documented how it is done right.</p>
<p>Prerequisites: Java, Ant, Python, cmake (I highly recommend to install all of those with Homebrew)</p>
<p>Open the terminal and switch to your working directory.</p>
<p>Clone the Git-Repository:<br />
<code>git clone git:&#47;&#47;github.com&#47;Itseez&#47;opencv.git<&#47;code></p>
<p>Switch to the folder and get the latest working version.<br />
<code>cd opencv</p>
<p>git checkout 2.4.10</p>
<p>mkdir build</p>
<p>cd build<br />
<&#47;code><br />
Create your C++ Compiling files<br />
<code>cmake -DBUILD_SHARED_LIBS=OFF ..<&#47;code></p>
<p>Compile the whole thing<br />
<code>sudo make -j8</p>
<p>sudo make install<&#47;code></p>
<p>Now open IntelliJ and go right to the project where you want to use OpenCV.</p>
<p>Go to File > Project Structure and add the created opencv-2410.jar located at <code>opencv&#47;build&#47;bin&#47;<&#47;code> as a module.</p>
<p>After applying go to Run > Debug Configurations and insert<br />
<code>-Djava.library.path=
<path to your buildfolder>&#47;opencv&#47;build&#47;lib<&#47;code></p>
<p>And finally, you are done. Now you can just import the libraries classes via org.opencv...</p>
<p>Hope this will help at least a few people.</p>
