TT_OpenWRT_Video_Fun
====================

Different video related stuff to do with an OpenWRT running router

Description
------------------
In this technology template you will find out how to do different video related stuff with and OpenWRT running router.

Examples:
- usb-webcam video streaming
- ip-cam video streaming

Requirements
------------------
- openwrt running router
- usb-webcam
- ethernet cables
- PC running linux
- some linux command-line knowledge

VideoStreaming - HowTo:
------------------
1. get the software needed
- telnet to the router
- opkg update 
- opkg install kmod-video-uvc mjpg-streamer
2. configure 
- edit the mjpg-streamer configuration file: nano /etc/config/mjpg-streamer, find the << option enabled          "0"  >> line and change from 0 to 1
- plug in the camera
- start mjpg-streamer: /etc/init.d/mjpg-streamer start
- OPTIONAL-> make mjpg-streamer autostart every time the router boots: /etc/init.d/mjpg-streamer enable
3. enjoy
- go to your browser and type in 192.168.1.1:8080/?action=stream
- change 192.168.1.1 with your routers internal ip, if its different

Resources
------------------
http://wiki.openwrt.org/doc/howto/webcam