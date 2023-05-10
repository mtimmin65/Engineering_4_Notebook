# Engineering_4_Notebook

&nbsp;

## Table of Contents
* [Launch_Pad_Part_1](#Launch_Pad_Part_1)
* [Launch_Pad_Part_2](#Launch_Pad_Part_2)
* [Launch_Pad_Part_3](#Launch_Pad_Part_3)
* [Launch_Pad_Part_4](#Launch_Pad_Part_4)
* [Crash avoidance 1](#Crash_avoidance_1)
* [Crash avoidance 2](#Crash_avoidance_2)
* [Landing Area 1](#Landing_Area_1)
* [Landing Area 2](#Landing_Area_2)
* [Morse Code 1](#Morse_Code_1)
* [Morse Code 2](#Morse_Code_2)
* [Onshape_Assignment_Template](#Onshape_Assignment_Template)
* [FEA_part1](#FEA_part1)
* [FEA_part2](#FEA_part2)
* [FEA_part3](#FEA_part3)
* [ring_and_spinner](#ring_and_spinner)
* [key_and_prop](#key_and_prop)
* [full_assembly](#full_assembly)
&nbsp;

## Launch_Pad_Part_1

### Assignment Description
make code that counts down from ten to zero and prints liftoff.

### Evidence

 ![Picture Name Here](images/maxcountdown1.gif)

### Code
``` python
import time
for x in range (10,0,-1):  #Range from 10,0 count down -1 each second
    print(x)
    time.sleep (1)  # Second between each number
print("Takeoff!")   # print this at 0
``` 

### Reflection

pretty simple assignment and I used some online reasources (google) to learn how to countdown.

## Launch_Pad_Part_2

### Assignment Description

make a red light blink for 10 second with a countdown and then print liftoff and turn on a green light.

### Evidence 

 ![Picture Name Here](images/maxcountdown2.gif)

### Wiring

 ![Picture Name Here](images/maxwiring1.jpg)

### Code
``` python
import time 
import board
import digitalio 

GreenLed = digitalio.DigitalInOut(board.GP13)
GreenLed.direction = digitalio.Direction.OUTPUT 
RedLed = digitalio.DigitalInOut(board.GP18) 
RedLed.direction = digitalio.Direction.OUTPUT 

for x in range (10,0,-1):  
    GreenLed.value = True #Turns led on intially
    time.sleep(0.5) # sleep half second
    print(x) # continues  countdown
    led1.value = False #turns led off
    time.sleep(0.5) # sleep other half second
while True:
    print("Takeoff!") 
    RedLed.value = True #Red Led turns on at end of countdown
    time.sleep(0.5) # Led turns off
 ``` 

### Reflection

a good review on using leds. pretty cool easy assignment.

## Launch_Pad_Part_3

### Assignment Description

press a button that starts what we did in the previouse assignment.

### Evidence 

![Picture Name Here](images/maxcountdown3.gif)

### Wiring

![Picture Name Here](images/maxwiring2.jpg)

### Code
``` python
import time 
import board
import digitalio

GreenLed = digitalio.DigitalInOut(board.GP13)  
GreenLed.direction = digitalio.Direction.OUTPUT
RedLed = digitalio.DigitalInOut(board.GP18)
RedLed.direction = digitalio.Direction.OUTPUT
button = digitalio.DigitalInOut(board.GP16) 
button.direction = digitalio.Direction.INPUT # Leds are output, Button is an Input
button.pull = digitalio.Pull.UP 

while True: 
     if button.value == False: # Button initializes code
          for x in range (10,0,-1):  
    GreenLed.value = True #Turns led on intially
    time.sleep(0.5) # sleep half second
    print(x) # continues  countdown
    led1.value = False #turns led off
    time.sleep(0.5) # sleep other half second
     while True:
         print("Takeoff!") 
         RedLed.value = True #Red Led turns on at end of countdown
         time.sleep(0.5) # Led turns off
``` 

### Reflection

I had difficulty with the direction of the button but i turn it and it worked.

## Launch_Pad_Part_4

### Assignment Description

now we have the countdown with leds and a start button we add 

### Evidence 

![Picture Name Here](images/maxcountdown4.gif)

### Wiring

This may not be applicable to all assignments. Anything where you wire something up, include the wiring diagram here. The diagram should be clear enough that I can recreate the wiring from scratch. 

### Code
``` python

servo.angle = 0

     if button.value == False: # Button initializes code
     for x in range (10,0,-1):  
     GreenLed.value = True #Turns led on intially
     time.sleep(0.5) # sleep half second
     print(x) # continues  countdown
     led1.value = False #turns led off
     time.sleep(0.5) # sleep other half second
     while True:
     print("Takeoff!") 
     RedLed.value = True #Red Led turns on at end of countdown
     time.sleep(0.5) # Led turns off
     while True:
          print("liftoff!")     #say liftoff
          led2.value = True
          servo.angle = 180  #Turn Servo from 0 degrees to 180
          time.sleep(0.5)

``` 

### Reflection


## Crash_avoidance_1

### Assignment discription

### Evidence
![Picture Name Here](images/maxcrash1.gif)
### Wiring

### Code
``` python
import board 
import adafruit_mpu6050
import busio 
import time
import digitalio 


sda_pin = board.GP16  # Accelermatoer 
scl_pin = board.GP17
i2c = busio.I2C(scl_pin, sda_pin)
mpu = adafruit_mpu6050.MPU6050(i2c)


while True:
    print(mpu.acceleration)   # print x y and z values
    time.sleep(.5)
``` 
### Reflection

## Crash_avoidance_2

### Assignment discription

### Evidence
![Picture Name Here](images/maxcrash2.gif)
### Wiring

### Code
``` python
import board 
import adafruit_mpu6050
import busio 
import time
import digitalio 

led = digitalio.DigitalInOut(board.GP1) 
led.direction = digitalio.Direction.OUTPUT
sda_pin = board.GP16  # Accelermatoer 
scl_pin = board.GP17
i2c = busio.I2C(scl_pin, sda_pin)
mpu = adafruit_mpu6050.MPU6050(i2c)


while True:
    print(mpu.acceleration)   # print x y and z values
    time.sleep(.5)

    if mpu.acceleration[0] < -9 or mpu.acceleration[0] > 9: # if x value less then -9 ot greater than 9
        led.value = True  # at these values, 90 degrees, led turns on.
    else:
        led.value = False  #if its not then the led is off
  ``` 
### Reflection

## Crash_avoidance_3

### Assignment discription

### Evidence
![Picture Name Here](images/maxcrash3.gif)
### Wiring

### Code
``` python
import board  #import shit
import adafruit_mpu6050
import busio 
import time
import digitalio 
import terminalio
import displayio
from adafruit_display_text import label
import adafruit_displayio_ssd1306

displayio.release_displays()
sda_pin = board.GP14   #setup pico
scl_pin = board.GP15
i2c = busio.I2C(scl_pin, sda_pin)
display_bus = displayio.I2CDisplay(i2c, device_address=0x3d, reset=board.GP28)
display = adafruit_displayio_ssd1306.SSD1306(display_bus, width=128, height=64)
led_red = digitalio.DigitalInOut(board.GP18)   #led setup
led_red.direction = digitalio.Direction.OUTPUT

mpu = adafruit_mpu6050.MPU6050(i2c, address=0x68) #accelerometer

 
while True:
    print(mpu.acceleration)   #say the values
    time.sleep(.5)
    print("Gyro X:%.2f, Y: %.2f, Z: %.2f rad/s" % (mpu.gyro))
    splash = displayio.Group()  #create the display group

    title = "ANGULAR VELOCITY" #add title block to display group
    text_area = label.Label(terminalio.FONT, text=title, color=0xFFFF00, x=5, y=5)
    splash.append(text_area) 

    title = f"x: {mpu.gyro[0]}" 
    text_area = label.Label(terminalio.FONT, text=title, color=0xFFFF00, x=5, y=15) # determines and prints x value
    splash.append(text_area)  
    
    title = f"y: {mpu.gyro[0]}" 
    text_area = label.Label(terminalio.FONT, text=title, color=0xFFFF00, x=5, y=30) # figures and and says y value
    splash.append(text_area) 

    title = f"z: {mpu.gyro[0]}" 
    text_area = label.Label(terminalio.FONT, text=title, color=0xFFFF00, x=5, y=45) # same thing with z
    splash.append(text_area)


    display.show(splash) #send display group to screen
    if mpu.acceleration[0] < -9 or mpu.acceleration[0] > 9:
        led_red.value = True  #at 90 degrees led is on

    else:
        led_red.value = False  #if not led is off
  ```
### Reflection


## Landing_area_1

### Assignment discription

### Evidnce
![Picture Name Here](images/maxlanding1.gif)
### wiring 

### Code 

### Reflection


## Landing_area_2

### Assignment discription

### Evidnce
![Picture Name Here](images/maxlanding2.gif)
### wiring 

### Code 

### Reflection
## FEA_part1

### Assignment discription

### Evidence
![Picture Name Here](images/maxfea1.PNG)

### Reflection


## FEA_part2

### Assignment discription

### Evidence
![Picture Name Here](images/maxfea2.png)

### Reflection


## FEA_part3

### Assignment discription

### Evidence
![Picture Name Here](images/maxfea3.png)

### Reflection

## ring_and_spinner

### Assignment discription

### Evidence
![Picture Name Here](images/max4.1.PNG)

### Reflection

## key_and_prop

### Assignment discription

### Evidence
![Picture Name Here](images/max4.2.PNG)

### Reflection

## full_assembly

### Assignment discription

### Evidence
![Picture Name Here](images/max4.3.PNG)

### Reflection


## Media Test

Your readme will have various images and gifs on it. Upload a test image and test gif to make sure you've got the process figured out. Pick whatever image and gif you want!

### Test Link
[click here for fun supriz3 :) ](https://www.youtube.com/watch?v=dQw4w9WgXcQ)
### Test Image
 ![Picture Name Here](images/Capture.PNG)
### Test GIF
 ![Picture Name Here](images/giphy.gif)
