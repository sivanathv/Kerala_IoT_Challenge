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

<img src="https://user-images.githubusercontent.com/42141371/147653714-ae3bd4f6-3d1e-40ab-980a-969db8f7584c.png" alt="Arduino UNO" width="500" height="281">

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
[![Hello World LED Blinking](https://user-images.githubusercontent.com/42141371/147594549-f0fd04db-4021-4392-a5e3-55f934bdce98.png)](https://user-images.githubusercontent.com/42141371/147592332-c1bef299-fce7-4259-ad8d-5d14d0021d13.mp4)
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
[![Traffic Light](https://user-images.githubusercontent.com/42141371/147594549-f0fd04db-4021-4392-a5e3-55f934bdce98.png)](https://user-images.githubusercontent.com/42141371/147639177-00913916-978b-44c9-a86e-03c30ed109b2.mp4)
<a name="chase"></a>
## 3. LED Chasing Effect
### Circuit
![LED Chasing Effect](https://user-images.githubusercontent.com/42141371/147650079-a70cca07-3e0f-4a98-8bb7-3f7ca0e0f5ad.png "LED Chasing Effect")
### Code
```c++
int num=12; //No. of LEDs
void setup()
{
  for (int i=2;i<num+2;i++)
  {pinMode(i, OUTPUT);}
}

void loop()
{
  for (int i=2;i<num+2;i++)
  {
    digitalWrite(i,HIGH);
    delay(50); //wait for 50 milliseconds
  }
  for (int i=2;i<num+2;i++)
  {
    digitalWrite(i,LOW);
    delay(50); //wait for 50 milliseconds
  }
}
```
### Working Video
[![Hello World LED Blinking](https://user-images.githubusercontent.com/42141371/147594549-f0fd04db-4021-4392-a5e3-55f934bdce98.png)](https://user-images.githubusercontent.com/42141371/147650934-0d98e046-0646-4c82-952b-1868d1e0dc0c.mp4)
<a name="button"></a>
## 4. Button Controlled LED
### Circuit
![Button Controlled LED](https://user-images.githubusercontent.com/42141371/147650211-291d98e1-0c1a-4677-af8f-bf5a285add58.png "Button Controlled LED")
### Code
```c++
int led=8; //LED pin
int button=4; //button pin
void setup()
{
  pinMode(led,OUTPUT);
  pinMode(button,INPUT);
}
void loop()
{
  if(digitalRead(button)==HIGH) //read the digital value in button
  {digitalWrite(led,HIGH);} //LED on
  else
  {digitalWrite(led,LOW);} //LED off
}
```
### Working Video
[![LED Chasing Effect](https://user-images.githubusercontent.com/42141371/147594549-f0fd04db-4021-4392-a5e3-55f934bdce98.png)](https://user-images.githubusercontent.com/42141371/147651006-88087db4-df5f-42c5-8760-112afb049c99.mp4)
<a name="buzzer"></a>
## 5. Buzzer
### Circuit
![Buzzer](https://user-images.githubusercontent.com/42141371/147650284-3488290c-0c8c-43d7-a958-d54455200712.png "Buzzer")
### Code
```c++
void setup()
{
 pinMode(10,OUTPUT);
}
void loop()
{
  digitalWrite(10,HIGH);
}
```
### Working Video
[![Buzzer](https://user-images.githubusercontent.com/42141371/147594549-f0fd04db-4021-4392-a5e3-55f934bdce98.png)](https://user-images.githubusercontent.com/42141371/147651058-adfa6a53-5818-4b17-a56c-48e41d638368.mp4)
<a name="rgb"></a>
## 6. RGB LED
### Circuit
![RGB LED](https://user-images.githubusercontent.com/42141371/147650353-cb7445a4-a3b0-4d39-b31c-3f551884dab3.png "RGB LED")
### Code
```c++
int val;
void setup()
{
  pinMode(11,OUTPUT); //red pin
  pinMode(10,OUTPUT); //blue pin
  pinMode(9,OUTPUT); //green pin
  Serial.begin(9600);
}
void loop()
{
  val= random(0,255);
  analogWrite(11,val);
  analogWrite(10,255-val);
  analogWrite(9,128-val);
  Serial.println(val); //print value in serial monitor
}
```
### Working Video
[![RGB LED](https://user-images.githubusercontent.com/42141371/147594549-f0fd04db-4021-4392-a5e3-55f934bdce98.png)](https://user-images.githubusercontent.com/42141371/147651111-370e901f-2e3e-4735-92b0-77d76352cef9.mp4)
<a name="ldr"></a>
## 7. LDR Light Sensor
### Circuit
![LDR Light Sensor](https://user-images.githubusercontent.com/42141371/147650465-0517fbce-5502-40a0-b733-3173c0df46ad.png "LDR Light Sensor")
### Code
```c++
int ldr=A0; //analog pin for LDR
int led=11; //LED pin
int light;
void setup()
{
  pinMode(led,OUTPUT);
  pinMode(ldr,INPUT);
  Serial.begin(9600);
}
void loop()
{
  light=analogRead(ldr); //read analog value from LDR
  Serial.println(light); //print value on serial monitor
  analogWrite(led,light/4); //intensity of LED depends on analog value
  delay(10);
}
```
### Working Video
[![LDR Light Sensor](https://user-images.githubusercontent.com/42141371/147594549-f0fd04db-4021-4392-a5e3-55f934bdce98.png)](https://user-images.githubusercontent.com/42141371/147651162-dee65723-c9de-4fed-8caa-be018b63b66a.mp4)
<a name="flame"></a>
## 8. Flame Sensor
### Circuit
![Flame Sensor](https://user-images.githubusercontent.com/42141371/147650570-ce26a84a-3188-49a1-93e8-837a029dad5b.png "Flame Sensor")
### Code
```c++
int buzz=12; //buzzer pin 
int sense=A0; //Flame sensor pin
int flame;
void setup()
{
  pinMode(buzz, OUTPUT); 
  pinMode(sense, INPUT); 
  Serial.begin(9600);
}
void loop()
{
  flame=analogRead(sense); //analog value from sensor
  Serial.println(flame); //print value on serial monitor
  if (flame>=115)
  {
    digitalWrite(buzz, HIGH); //buzzer turns on
  }
  else
  {
    digitalWrite(buzz, LOW); //buzzer turns off
  }
  delay(10);
}
```
### Working Video
[![Flame Sensor](https://user-images.githubusercontent.com/42141371/147594549-f0fd04db-4021-4392-a5e3-55f934bdce98.png)](https://user-images.githubusercontent.com/42141371/147651208-216cc8f7-bc0a-4a53-a27a-4e04785f6190.mp4)
<a name="lm35"></a>
## 9. LM35 Temperature Sensor
### Circuit
![LM35 Temperature Sensor](https://user-images.githubusercontent.com/42141371/147650494-bb8e1af6-b310-4b22-be21-fd99c6827434.png "LM35 Temperature Sensor")
### Code
```c++
int val;
float degree; //degree in decimal
void setup()
{
  pinMode(A0,INPUT);
  Serial.begin(9600);
}
void loop()
{
  val=analogRead(A0); //read value from sensor
  degree= ((val-20.0)*165.0/338.0)-40.0; //temperature calculation
  Serial.print("Temp ");
  Serial.print(degree);
  Serial.println(" C");
}
```
### Working Video
[![LM35 Temperature Sensor](https://user-images.githubusercontent.com/42141371/147594549-f0fd04db-4021-4392-a5e3-55f934bdce98.png)](https://user-images.githubusercontent.com/42141371/147651248-b88c1fb7-a752-4d93-8e70-3c013b0b15fd.mp4)
