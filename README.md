#!/usr/bin/python
import RPi.GPIO as GPIO
import time
 
#GPIO SETUP
channel = 21
GPIO.setmode(GPIO.BCM)
GPIO.setup(channel, GPIO.IN)
 
def callback(channel):
        if GPIO.input(channel):
                print ("High Level of Water!")
        else:
                print ("Low Level of Water!")
        
        
 
GPIO.add_event_detect(channel, GPIO.BOTH, bouncetime=10)  # event detections for the pins goes HIGH or LOW
GPIO.add_event_callback(channel, callback)  # call back for repeating the function 
 
# infinite loop
while True:
        time.sleep(1)


You can copy and paste the code if you want
No copyright for this code
