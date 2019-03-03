# KnoParking
A program with complex architecture that detects motion via a ESP8266 with a HCSR04 Motion Detector. Once motion is detected, buffered images are sent to a Web Server where a packet is sent back to the Rasberry Pi. The Rasberry Pi captures a photo using the Camera Module. Finally, it is sent back to the server. The server the buffered images to a Node JS server that is being ran on a third program. Via sockets, the website could be wrapped with a Java program, however, it is not preferable because the client machine would need to run programs in two separate IDEs. Using a raw socket server implementation, the website can be populated with images of a security breach!

# Prerequisites
The Raspberry Pi program will not run unless the terminal command vcgencmd get_camera returns supported=1 detected=1. If the return is supported=0 detected=0, the Raspberry Pi cannot use a Camera Module. If the return is supported=1 detected=0, follow the following steps:

Check to make sure ribbon of the camera is facing the right way, and is all the way in the connector slot.
Check to make sure ribbon is in proper connector slot: the one between the ethernet port and the HDMI port.
Try enabling the camera interface in the config settings. Run sudo apt-get update and sudo apt-get upgrade. Then run sudo raspi-config. If the camera option doesn't appear, select the Update option, restart the raspberry pi, and then go back and select the Interfacing Options, select Camera, and enable it. If it does appear, select camera and enable it, run vcgencmd get_camera again, and the camera should be detected.
For the ESP8266 Motion Detector, to be added.

For the website, to be added.

# Deployment
Point the camera of the Raspberry Pi in a direction so it can see the liscence plate. Download the contents of the Raspberry Pi folder on the Raspberry Pi. ls to the folder and do java -cp ":jrpicam-1.1.1.jar:" CameraSender to run the CameraSender.class file.

# Further Expansion
This program can be expanded to maintain a running memory of cars and their license plates in a parking lot. We plan on adding this as an extension to the project.

# Built With
JRPiCam, the Java version of the RPi Camera Modu API.
Info
This program was used for PioneerHacks II 2019.

# Authors
* Akshay Trivedi
* Ishan Jain
* Aditya Prerepa
