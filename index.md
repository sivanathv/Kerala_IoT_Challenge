# Kerala IoT Challenge
## Introduction
Foxlab Makerspace in association with GTech - Group of Technology Companies in Kerala is launching our prestigious program  “Kerala IoT Challenge 2021”,  with a vision to mould 100 IoT experts in Kerala, hosting on the MuLearn platform. Kerala IoT Challenge is a program designed in 4 levels followed by a hackathon to identify and train quality industry leaders in the IoT domain, while any novice learner can start with layer 1 and others can enter laterally to the desired layer after an evaluation.
## Program Structure:
### [Level 1: Basic Electronics and Arduino](#level1)
### Level 2: Introduction to IoT
### Level 3: IoT Intermediate
### Level 4: IoT Advanced

<a name='level1'></a>
# Level 1: Basic Electronics & Arduino
## Introduction to Arduino
Arduino is an open-source electronics platform based on easy-to-use hardware and software. Arduino boards are able to read inputs - light on a sensor, a finger on a button, or a Twitter message - and turn it into an output - activating a motor, turning on an LED, publishing something online. You can tell your board what to do by sending a set of instructions to the microcontroller on the board. To do so you use the Arduino programming language (based on Wiring), and the Arduino Software (IDE), based on Processing.

![Photo by Harrison Broadbent on Unsplash](https://github.com/sivanathv/Kerala_IoT_Challenge/blob/main/Images/harrison-broadbent-fZB51omnY_Y-unsplash.jpg "Arduino UNO")

## Experiments
  1. [Hello World LED Blinking](#blink)
  2. [Traffic Light](#traffic)
  3. [LED Chasing Effect](#chase)
  4. [Button Controlled LED](#button)
  5. [Buzzer](#buzzer)
  6. [RGB LED](#rgb)
  7. [LDR Light Sensor](#ldr)
  8. [Flame Sensor](#flame)
  9. [LM35 Temperature Sensor](#lm35)
  10. [IR Remote Control Using TSOP](#ir)
  11. [Potentiometer Analog Value Reading](#pot)
  12. [7 Segment Display](#7)

<a name='blink'></a>
## 1. Hello World LED Blinking
### Circuit
![Blink](https://user-images.githubusercontent.com/42141371/147439431-b33bf2d9-e204-4fd3-8f45-a0c2bf272e95.png "LED Blinking")
### Code
```c++
void setup()
{pinMode(13, OUTPUT);} // Define LED pin

void loop()
{
  digitalWrite(13, HIGH);
  delay(1000); // Wait for 1000 millisecond(s)
  digitalWrite(13, LOW);
  delay(1000); // Wait for 1000 millisecond(s)
}
```
### Working video

<a name='traffic'></a>
## 2. Traffic Light
### Circuit
![Traffic](https://user-images.githubusercontent.com/42141371/147449316-8cab4b32-3f26-4a36-9c09-2133391f27f3.png "Traffic light")
### Code
```c++
int red =13;
int yellow =11;
int green =9;
void setup()
{
pinMode(red, OUTPUT);
pinMode(yellow, OUTPUT);
pinMode(green, OUTPUT);
}
void loop()
{
digitalWrite(green, HIGH);// turn on green LED
delay(2500);
digitalWrite(green, LOW);// turn off green LED
digitalWrite(yellow, HIGH);// turn on yellow LED
delay(2500);
digitalWrite(yellow, LOW);// turn off yellow LED
digitalWrite(red, HIGH);// turn on red LED
delay(2500);
digitalWrite(red, LOW);// turn off red LED
delay(500);
//turn on all LEDs
digitalWrite(green, HIGH);
digitalWrite(yellow, HIGH);
digitalWrite(red, HIGH);
delay(500);
//turn off all LEDs
digitalWrite(green, LOW);
digitalWrite(yellow, LOW);
digitalWrite(red, LOW);
delay(500);
}
```
### Working Video

<a name="chase"></a>
## 3. LED Chasing Effect
### Circuit
