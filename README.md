# LBeacon-Zigbee
## Zigbee on Respberry Pi

## Library

> The library we use is "libxbee3."<br />
> The Original repository of "libxbee3" is https://github.com/attie/libxbee3

> This repository is for the use of Zigbee module(xbee S2) on Respberry pi.<br />The following is the manual of Zigbee(xbee Series 2):
https://www.digi.com/resources/documentation/digidocs/PDFs/90000976.pdf


### === Environment ===
The OS on the Respberry Pi is RASPBIAN STRETCH LITE 2017-11-29 version.<br />
The official website of Raspberry Pi is https://www.raspberrypi.org<br />
The download link of RASPBIAN STRETCH LITE(2017-11-29 version) is <br />http://vx2-downloads.raspberrypi.org/raspbian_lite/images/raspbian_lite-2017-12-01/2017-11-29-raspbian-stretch-lite.zip


### === Building libxbee3 library ===
If you are building libxbee, then there are a number of options avaliable to you.<br />
Initially you should run the following command:
<pre><code>$ make configure</code></pre>
	
This will retrieve a default `config.mk` that is suitable for your Respberry Pi.<br />
In our project you need to<br />
un-comment `OPTIONS+=       XBEE_LOG_LEVEL=100`<br />
comment `OPTIONS+=       XBEE_LOG_RX_DEFAULT_OFF`<br />
comment `OPTIONS+=       XBEE_LOG_TX_DEFAULT_OFF`<br />
un-comment `OPTIONS+=       XBEE_NO_RTSCTS`<br />

You should review this file and then run the following command:
<pre><code>$ make all</code></pre>

After the build process has completed, you should find suitable files in **./lib**.<br />
E.g: for a Unix-like OS you can expect to find **.so** and **.a** files<br />
<<<<<<< HEAD
        for Windows you can expect to find a **.dll** file<br />
=======
        for Windows you can expect to find a **.dll** file<br />
>>>>>>> 2c6dd0ec2418b1b4852bea36029253368944b631

It is highly recommended that you don't modify any of the build system.


### === Installation of libxbee library ===
To install libxbee simply type (you will require **root permissions**):
<pre><code>$ sudo make install</code></pre>


### === Usage ===
Compile your applications, including **xbee.h** in the relevant source files.<br />
Ensure you link with libxbee (e.g: using `gcc -lxbee`)

If you are compiling the object file directly into your executable instead
of making use of the library,<br />you must include the following link flags:
`-lpthread -lrt`<br />

## Setup Zigbee
Push later or maybe put on Gitbook for better Reading experience 

## Tools
<<<<<<< HEAD
Todo
=======
Todo
>>>>>>> 2c6dd0ec2418b1b4852bea36029253368944b631
