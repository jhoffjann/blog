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
