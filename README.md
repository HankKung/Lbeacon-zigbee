# LBeacon-Zigbee
## Zigbee on Respberry Pi

## Library

> The library we use is "libxbee3."<br />
> The Original repository of "libxbee3" is https://github.com/attie/libxbee3

> This repository is for the use of Zigbee module(xbee S2C) on Respberry pi.<br />
The following is the manual of XBEE S2C: <br />
https://www.digi.com/resources/documentation/digidocs/pdfs/90002002.pdf


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
        for Windows you can expect to find a **.dll** file<br />

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
Config now can be upload by program, but still something need to set up before start using Zigbee. <br />
It is essential for Connection and Configure through Serial Port. <br />
In this project, we use `ZIGBEE TH Reg` as our main Function. The following config is for it.

1. Open XCTU (Download Link: https://www.digi.com/products/xbee-rf-solutions/xctu-software/xctu)<br />
2. Add the radio you decide to setup<br />
3. click the radio you decide to setup<br />
4. Change AP (API Output Mode) to `API enabled[1]`, change D6 (DIO6 Configuration) to `Disable[0]` <br />
   and change D7 (DIO7 Configuration) to `Disable[0]`<br />
   
Manual For XCTU: https://www.digi.com/resources/documentation/digidocs/PDFs/90001458-13.pdf
