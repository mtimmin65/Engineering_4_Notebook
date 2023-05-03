# Engineering_4_Notebook

&nbsp;

## Table of Contents
* [Launch_Pad_Part_1](#Launch_Pad_Part_1)
* [Launch_Pad_Part_2](#Launch_Pad_Part_2)
* [Launch_Pad_Part_3](#Launch_Pad_Part_3)
* [Launch_Pad_Part_4](#Launch_Pad_Part_4)
* [FEA_Part1](#)
FEA_Part2
FEA_Part3
* [Onshape_Assignment_Template](#Onshape_Assignment_Template)

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

This may not be applicable to all assignments. Anything where you wire something up, include the wiring diagram here. The diagram should be clear enough that I can recreate the wiring from scratch. 

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

Write your assignment description here. What is the purpose of this assignment? It should be at least a few sentences.

### Evidence 

Pictures / Gifs of your work should go here. You need to communicate what your thing does. 

### Wiring

This may not be applicable to all assignments. Anything where you wire something up, include the wiring diagram here. The diagram should be clear enough that I can recreate the wiring from scratch. 

### Code
Give me a link to your code. [Something like this](https://github.com/millerm22/Engineering_4_Notebook/blob/main/Raspberry_Pi/hello_world.py). Don't make me hunt through your folders, give me a nice link to click to take me there! Remember to **COMMENT YOUR CODE** if you want full credit. 

### Reflection


&nbsp;

## Media Test

Your readme will have various images and gifs on it. Upload a test image and test gif to make sure you've got the process figured out. Pick whatever image and gif you want!

### Test Link
[click here for fun supriz3 :) ](https://www.youtube.com/watch?v=dQw4w9WgXcQ)
### Test Image
 ![Picture Name Here](images/Capture.PNG)
### Test GIF
 ![Picture Name Here](images/giphy.gif)
