# Kerala IoT Challenge
## Introduction
Foxlab Makerspace in association with GTech - Group of Technology Companies in Kerala is launching our prestigious program  “Kerala IoT Challenge 2021”,  with a vision to mould 100 IoT experts in Kerala, hosting on the MuLearn platform. Kerala IoT Challenge is a program designed in 4 levels followed by a hackathon to identify and train quality industry leaders in the IoT domain, while any novice learner can start with layer 1 and others can enter laterally to the desired layer after an evaluation.
## Program Structure:
### [Level 1: Basic Electronics and Arduino](https://sivanathv.github.io/Level-1-IoT/)
### Level 2: Introduction to IoT
### Level 3: IoT Intermediate
### Level 4: IoT Advanced

<a name='level1'></a>
# Level 1: Basic Electronics & Arduino
## Introduction to Arduino
Arduino is an open-source electronics platform based on easy-to-use hardware and software. Arduino boards are able to read inputs - light on a sensor, a finger on a button, or a Twitter message - and turn it into an output - activating a motor, turning on an LED, publishing something online. You can tell your board what to do by sending a set of instructions to the microcontroller on the board. To do so you use the Arduino programming language (based on Wiring), and the Arduino Software (IDE), based on Processing.

![Photo by Harrison Broadbent on Unsplash](https://user-images.githubusercontent.com/42141371/147653714-ae3bd4f6-3d1e-40ab-980a-969db8f7584c.png "Arduino UNO")

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
  12. [7-Segment Display](#7)
  13. [Assignments](#assign)

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
#### Virtual Simulation
[![Hello World LED Blinking](https://user-images.githubusercontent.com/42141371/147594549-f0fd04db-4021-4392-a5e3-55f934bdce98.png)](https://user-images.githubusercontent.com/42141371/147592332-c1bef299-fce7-4259-ad8d-5d14d0021d13.mp4)
#### Actual Simulation
[![LED Blink](https://user-images.githubusercontent.com/42141371/156929091-70ecedef-c29e-4fd8-866b-dc6469160eff.png)](https://user-images.githubusercontent.com/42141371/156928344-f8274cd9-22fb-4a45-9c52-34d6962859c3.mp4)
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
#### Virtual Simulation
[![Traffic Light](https://user-images.githubusercontent.com/42141371/147594549-f0fd04db-4021-4392-a5e3-55f934bdce98.png)](https://user-images.githubusercontent.com/42141371/147639177-00913916-978b-44c9-a86e-03c30ed109b2.mp4)
#### Actual Simulation
[![Traffic light](https://user-images.githubusercontent.com/42141371/156929928-07d33c10-c779-45e2-a814-db09164aa359.png)](https://user-images.githubusercontent.com/42141371/156930082-5e20e29e-c9e6-4f8b-914d-3fe7ba87b11e.mp4)
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
#### Virtual Simulation
[![LED Chasing Effect](https://user-images.githubusercontent.com/42141371/147594549-f0fd04db-4021-4392-a5e3-55f934bdce98.png)](https://user-images.githubusercontent.com/42141371/147650934-0d98e046-0646-4c82-952b-1868d1e0dc0c.mp4)
#### Actual Simulation
[![LED chase](https://user-images.githubusercontent.com/42141371/156930749-93c12c56-e0f6-41a8-98b1-436278d233a4.png)](https://user-images.githubusercontent.com/42141371/156930740-69e1f40e-7b60-483d-b2a9-9d36b6773a08.mp4)
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
#### Virtual Simulation
[![Button Controlled LED](https://user-images.githubusercontent.com/42141371/147594549-f0fd04db-4021-4392-a5e3-55f934bdce98.png)](https://user-images.githubusercontent.com/42141371/147651006-88087db4-df5f-42c5-8760-112afb049c99.mp4)
#### Actual Simulation
[![Push button LED](https://user-images.githubusercontent.com/42141371/156930835-97892b24-b8b9-41b1-884d-1bf33f3a92e3.png)](https://user-images.githubusercontent.com/42141371/156930883-8520961d-1931-436c-828a-761fcbaa7dd6.mp4)
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
#### Virtual Simulation
[![Buzzer](https://user-images.githubusercontent.com/42141371/147594549-f0fd04db-4021-4392-a5e3-55f934bdce98.png)](https://user-images.githubusercontent.com/42141371/147651058-adfa6a53-5818-4b17-a56c-48e41d638368.mp4)
#### Actual Simulation
[![Buzzer](https://user-images.githubusercontent.com/42141371/156930910-24a3ab22-12cd-49e6-bf38-a34ed7b57793.png)](https://user-images.githubusercontent.com/42141371/156930982-bf02cf13-3cf8-4af5-863c-dee60ef6fd71.mp4)
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
#### Virtual Simulation
[![RGB LED](https://user-images.githubusercontent.com/42141371/147594549-f0fd04db-4021-4392-a5e3-55f934bdce98.png)](https://user-images.githubusercontent.com/42141371/147651111-370e901f-2e3e-4735-92b0-77d76352cef9.mp4)
#### Actual Simulation
[![RGB light](https://user-images.githubusercontent.com/42141371/156930998-0859008e-8a86-47d0-a116-561c72ff9261.png)](https://user-images.githubusercontent.com/42141371/156931007-53fe05e9-c4fb-42b8-b643-4e2ffc282ecc.mp4)
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
  analogWrite(led,light/100); //intensity of LED depends on analog value
  delay(500);
}
```
### Working Video
#### Virtual Simulation
[![LDR Light Sensor](https://user-images.githubusercontent.com/42141371/147594549-f0fd04db-4021-4392-a5e3-55f934bdce98.png)](https://user-images.githubusercontent.com/42141371/147651162-dee65723-c9de-4fed-8caa-be018b63b66a.mp4)
#### Actual Simulation
[![LDR light sensor](https://user-images.githubusercontent.com/42141371/156931108-fc9fbc0e-8b37-4080-84bc-9c5d76f26e93.png)](https://user-images.githubusercontent.com/42141371/156931122-27f9326e-f8ac-49d0-978e-af1151f33854.mp4)
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
  delay(200);
}
```
### Working Video
#### Virtual Simulation
[![Flame Sensor](https://user-images.githubusercontent.com/42141371/147594549-f0fd04db-4021-4392-a5e3-55f934bdce98.png)](https://user-images.githubusercontent.com/42141371/147651208-216cc8f7-bc0a-4a53-a27a-4e04785f6190.mp4)
#### Actual Simulation
[![Flame sensor](https://user-images.githubusercontent.com/42141371/156931170-498194ae-67ec-465f-9faa-727bfe9aa4c6.png)](https://user-images.githubusercontent.com/42141371/156931197-85d5e5fe-8a8a-4386-8c76-dd9dcc308bb2.mp4)
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
#### Virtual Simulation
[![LM35 Temperature Sensor](https://user-images.githubusercontent.com/42141371/147594549-f0fd04db-4021-4392-a5e3-55f934bdce98.png)](https://user-images.githubusercontent.com/42141371/147651248-b88c1fb7-a752-4d93-8e70-3c013b0b15fd.mp4)
#### Actual Simulation
[![Temp sensor](https://user-images.githubusercontent.com/42141371/156931223-ae6b00be-2314-4733-b8f4-5342a872a5f2.png)](https://user-images.githubusercontent.com/42141371/156931221-a1926df0-b51a-4175-b747-a189af1f57a4.mp4)
<a name="ir"></a>
## 10. IR Remote Control Using TSOP
![TSOP1738](https://user-images.githubusercontent.com/42141371/159976924-ec9f23fe-3b69-4e91-b594-7780b3799da2.png "TSOP1738 Sensor")
### Circuit
![IR Remote Control Using TSOP](https://user-images.githubusercontent.com/42141371/156557219-5d116a19-9d02-4f34-a4e3-58fde902468a.png "IR Remote Control Using TSOP")
### Code
#### Version 2
```c++
#include <IRremote.h>
int IRpin=11;	//initialising IR pin
IRrecv Sensor(IRpin);	//IR reciever as "Sensor"
decode_results rslt;	//decode results into "rslt"

void setup()
{
  Sensor.enableIRIn();
  Serial.begin(9600);
  pinMode(7,OUTPUT);
  pinMode(6,OUTPUT);
  pinMode(5,OUTPUT);
  pinMode(4,OUTPUT);
  pinMode(3,OUTPUT);
  pinMode(2,OUTPUT);
  pinMode(8,INPUT);
}

void loop()
{
  if(Sensor.decode(&rslt))  //without this condition, the serial monitor will print '0' continously
  {
    Serial.println(rslt.value, HEX);  //to print the value in HEX code
  	LED(); //all LEDs off and all LEDs ON
    Sensor.resume();
  }
}  
void LED()
{
    if (rslt.value==0xFD00FF) //The hex code could be different in actual simulation (depends on the remote)
    {
      if(digitalRead(8)==0)
      {
        for(int i=8;i--;i>=2)
        {digitalWrite(i,1);} //LEDs ON
      }
      else
      {
        for(int i=8;i--;i>=2)
      	{digitalWrite(i,0);} //LEDs OFF
  	  }
    }
}
```
#### Version 3
```c++
#include <IRremote.h>
int IRpin=11;  //initialising IR pin

void setup()
{
  IrReceiver.begin(IRpin, ENABLE_LED_FEEDBACK);
  Serial.begin(9600);
  pinMode(7,OUTPUT);
  pinMode(6,OUTPUT);
  pinMode(5,OUTPUT);
  pinMode(4,OUTPUT);
  pinMode(3,OUTPUT);
  pinMode(2,OUTPUT);
  pinMode(8,INPUT);
}

void loop()
{
  if(IrReceiver.decode())  //without this condition, the serial monitor will print '0' continously
  {
    Serial.println(IrReceiver.decodedIRData.decodedRawData, HEX);  //to print value in HEX code
    LED(); //all LEDs off and all LEDs ON
    IrReceiver.resume();
  }
}  
void LED()
{
    if (IrReceiver.decodedIRData.decodedRawData==0xFD00FF) //The hex code could be different in actual simulation (depends on the remote)
    {
      if(digitalRead(8)==0)
      {
        for(int i=8;i--;i>=2)
        {digitalWrite(i,1);} //LEDs ON
      }
      else
      {
        for(int i=8;i--;i>=2)
        {digitalWrite(i,0);} //LEDs OFF
      }
    }
}
```
### Working Video
#### Virtual Simulation
[![IR Remote Control Using TSOP](https://user-images.githubusercontent.com/42141371/147594549-f0fd04db-4021-4392-a5e3-55f934bdce98.png)](https://user-images.githubusercontent.com/42141371/156557808-94e6825d-8916-4444-9c05-df67e2966d6f.mp4)
#### Actual Simulation
[![TSOP Remote](https://user-images.githubusercontent.com/42141371/159973968-d715ca46-593d-4c2f-b866-58a27ae92a4c.png)](https://user-images.githubusercontent.com/42141371/159973708-44e38480-55ae-488a-92d4-f3130ea2633a.mp4)
<a name='pot'></a>
## 11. Potentiometer Analog Value Reading
![Potentiometer](https://user-images.githubusercontent.com/42141371/156624578-c2e02e0c-0a3b-4c5c-911e-e75ca56d9a35.png "Potentiometer") ![Potentiometer](https://user-images.githubusercontent.com/42141371/156624711-f5951159-1326-4591-8065-a17bf54e0b2a.png "Potentiometer")
### Circuit
![Potentiometer Analog Value Reading](https://user-images.githubusercontent.com/42141371/156591037-1178c8e6-caed-45b5-acfc-643e3b41b2f6.png "Potentiometer Analog Value Reading")
### Code
```c++
void setup()
{
  pinMode(A0, INPUT);
  Serial.begin(9600);
}
void loop()
{
  int pot=analogRead(A0); //Read value from potentiometer
  Serial.println(pot); //Print on Serial monitor
  delay(100); // Wait for 100 milliseconds
}
```
### Working Video
#### Virtual Simulation
[![Potentiometer Analog Value Reading](https://user-images.githubusercontent.com/42141371/147594549-f0fd04db-4021-4392-a5e3-55f934bdce98.png)](https://user-images.githubusercontent.com/42141371/156591570-c1c6959d-e382-4ffc-8a7f-8c66c6e73781.mp4)
#### Actual Simulation
[![Potentiometer](https://user-images.githubusercontent.com/42141371/156931280-e1afeecb-f022-476f-879e-e4f983684b72.png)](https://user-images.githubusercontent.com/42141371/156931304-a9ba95bb-1f47-46b7-ad48-2ee7596c5c9f.mp4)
<a name='7'></a>
## 12. 7-Segment Display
![7-Segment Display Configuration](https://user-images.githubusercontent.com/42141371/156623818-48aec383-050f-4258-8684-33fb0630f114.png "7 Segment Display Configuration")
### Circuit
![7-Segment Display](https://user-images.githubusercontent.com/42141371/156623615-ab0ea23c-2c10-4609-99d7-75303dd1dc35.png "7 Segment Display")
### Code
```c++
//Program to repeatedly count from 0 to 9 using 7-segment
//NOTE: In this program, DP terminal is grounded
int a=2;
int b=3;
int c=4;
int d=5;
int e=6;
int f=7;
int g=8;
void setup()
{
  for(int i=2;i<=8;i++)
  {pinMode(i, OUTPUT);}
}
void loop()
{
  zero();
  delay(1000);
  one();
  delay(1000);
  two();
  delay(1000);
  three();
  delay(1000);
  four();
  delay(1000);
  five();
  delay(1000);
  six();
  delay(1000);
  seven();
  delay(1000);
  eight();
  delay(1000);
  nine();
  delay(1000);
}
//Individual number functions:

void zero()
{
  digitalWrite(a,HIGH);
  digitalWrite(b,HIGH);
  digitalWrite(c,HIGH);
  digitalWrite(d,HIGH);
  digitalWrite(e,HIGH);
  digitalWrite(f,HIGH);
  digitalWrite(g,LOW);
}
void one()
{
  digitalWrite(a,LOW);
  digitalWrite(b,HIGH);
  digitalWrite(c,HIGH);
  digitalWrite(d,LOW);
  digitalWrite(e,LOW);
  digitalWrite(f,LOW);
  digitalWrite(g,LOW);
}
void two()
{
  digitalWrite(a,HIGH);
  digitalWrite(b,HIGH);
  digitalWrite(c,LOW);
  digitalWrite(d,HIGH);
  digitalWrite(e,HIGH);
  digitalWrite(f,LOW);
  digitalWrite(g,HIGH);
}
void three()
{
  digitalWrite(a,HIGH);
  digitalWrite(b,HIGH);
  digitalWrite(c,HIGH);
  digitalWrite(d,HIGH);
  digitalWrite(e,LOW);
  digitalWrite(f,LOW);
  digitalWrite(g,HIGH);
}
void four()
{
  digitalWrite(a,LOW);
  digitalWrite(b,HIGH);
  digitalWrite(c,HIGH);
  digitalWrite(d,LOW);
  digitalWrite(e,LOW);
  digitalWrite(f,HIGH);
  digitalWrite(g,HIGH);
}
void five()
{
  digitalWrite(a,HIGH);
  digitalWrite(b,LOW);
  digitalWrite(c,HIGH);
  digitalWrite(d,HIGH);
  digitalWrite(e,LOW);
  digitalWrite(f,HIGH);
  digitalWrite(g,HIGH);
}
void six()
{
  digitalWrite(a,HIGH);
  digitalWrite(b,LOW);
  digitalWrite(c,HIGH);
  digitalWrite(d,HIGH);
  digitalWrite(e,HIGH);
  digitalWrite(f,HIGH);
  digitalWrite(g,HIGH);
}
void seven()
{
  digitalWrite(a,HIGH);
  digitalWrite(b,HIGH);
  digitalWrite(c,HIGH);
  digitalWrite(d,LOW);
  digitalWrite(e,LOW);
  digitalWrite(f,LOW);
  digitalWrite(g,LOW);
}
void eight()
{
  digitalWrite(a,HIGH);
  digitalWrite(b,HIGH);
  digitalWrite(c,HIGH);
  digitalWrite(d,HIGH);
  digitalWrite(e,HIGH);
  digitalWrite(f,HIGH);
  digitalWrite(g,HIGH);
}
void nine()
{
  digitalWrite(a,HIGH);
  digitalWrite(b,HIGH);
  digitalWrite(c,HIGH);
  digitalWrite(d,HIGH);
  digitalWrite(e,LOW);
  digitalWrite(f,HIGH);
  digitalWrite(g,HIGH);
}
```
### Working Video
#### Virtual Simulation
[![7-Segment Display](https://user-images.githubusercontent.com/42141371/147594549-f0fd04db-4021-4392-a5e3-55f934bdce98.png)](https://user-images.githubusercontent.com/42141371/156624085-119d1a3f-004c-4cb9-a1f4-2cd474ee6caf.mp4)
#### Actual Simulation
[![7 segment counter](https://user-images.githubusercontent.com/42141371/159974762-836d7e17-ccab-4894-a14b-22dc6f2a3ca9.png)](https://user-images.githubusercontent.com/42141371/159974976-85aebc98-22dc-4b57-acf3-cd9ff18243cb.mp4)
<a name='assign'></a>
## Assignment 1
### Create an automatic night lamp model using LDR and LED
### Circuit
![LED & LDR](https://user-images.githubusercontent.com/42141371/159978035-4588ceee-c8a2-458f-8ce7-402b2ba88057.png "Automatic night lamp")
### Code
```c++
void setup()
{
  pinMode(12,OUTPUT);
  pinMode(A0,INPUT);
  Serial.begin(9600);
}

void loop()
{
  int ldr= analogRead(A0); //light value of LDR
  Serial.println(ldr);
  if (ldr<490)	//This condition can change in practical application
  {digitalWrite(12,1);}
  else
  {digitalWrite(12,0);}
  delay(100);
}
```
### Working Video
#### Virtual Simulation
[![LED_LDR](https://user-images.githubusercontent.com/42141371/147594549-f0fd04db-4021-4392-a5e3-55f934bdce98.png)](https://user-images.githubusercontent.com/42141371/159978660-7b57178c-085c-4582-9346-a1b224cca667.mp4)
#### Actual Simulation
[![LED & LDR](https://user-images.githubusercontent.com/42141371/159978374-5ebc0804-870f-4465-b21f-352608231065.png)](https://user-images.githubusercontent.com/42141371/159978216-eb8a447b-d339-43ce-80e0-78b96b737280.mp4)
## Assignment 2
### Create a Digital Dice using 7 Segment Display and Push Button
### Circuit
![Digital dice](https://user-images.githubusercontent.com/42141371/159980590-8d367f93-0b0d-4860-a6e5-6add1b10c9f8.png "Digital dice using 7 segment")
### Code
```c++
int a=2;
int b=3;
int c=4;
int d=5;
int e=6;
int f=7;
int g=8;
void setup()
{
  for(int i=2;i<=8;i++)
  {pinMode(i, OUTPUT);}
  pinMode(9,INPUT);
  Serial.begin(9600);
}
void loop()
{
  if (pulseIn(9,HIGH)) //to detect input from button
  {
    roll(); //Function to roll the dice
    int no=random(1,7); //random no. from 1 to 6
    Serial.println(no);
    switch (no)
    {case 1:one();break;
    case 2:two();break;
    case 3:three();break;
    case 4:four();break;
    case 5:five();break;
	case 6:six();break;}
  }
}
//Individual number functions:

void roll()
{
  one();delay(100);
  two();delay(100);
  three();delay(100);
  four();delay(100);
  five();delay(100);
  six();delay(100);
}

void zero()
{
  digitalWrite(a,HIGH);
  digitalWrite(b,HIGH);
  digitalWrite(c,HIGH);
  digitalWrite(d,HIGH);
  digitalWrite(e,HIGH);
  digitalWrite(f,HIGH);
  digitalWrite(g,LOW);
}
void one()
{
  digitalWrite(a,LOW);
  digitalWrite(b,HIGH);
  digitalWrite(c,HIGH);
  digitalWrite(d,LOW);
  digitalWrite(e,LOW);
  digitalWrite(f,LOW);
  digitalWrite(g,LOW);
}
void two()
{
  digitalWrite(a,HIGH);
  digitalWrite(b,HIGH);
  digitalWrite(c,LOW);
  digitalWrite(d,HIGH);
  digitalWrite(e,HIGH);
  digitalWrite(f,LOW);
  digitalWrite(g,HIGH);
}
void three()
{
  digitalWrite(a,HIGH);
  digitalWrite(b,HIGH);
  digitalWrite(c,HIGH);
  digitalWrite(d,HIGH);
  digitalWrite(e,LOW);
  digitalWrite(f,LOW);
  digitalWrite(g,HIGH);
}
void four()
{
  digitalWrite(a,LOW);
  digitalWrite(b,HIGH);
  digitalWrite(c,HIGH);
  digitalWrite(d,LOW);
  digitalWrite(e,LOW);
  digitalWrite(f,HIGH);
  digitalWrite(g,HIGH);
}
void five()
{
  digitalWrite(a,HIGH);
  digitalWrite(b,LOW);
  digitalWrite(c,HIGH);
  digitalWrite(d,HIGH);
  digitalWrite(e,LOW);
  digitalWrite(f,HIGH);
  digitalWrite(g,HIGH);
}
void six()
{
  digitalWrite(a,HIGH);
  digitalWrite(b,LOW);
  digitalWrite(c,HIGH);
  digitalWrite(d,HIGH);
  digitalWrite(e,HIGH);
  digitalWrite(f,HIGH);
  digitalWrite(g,HIGH);
}
void seven()
{
  digitalWrite(a,HIGH);
  digitalWrite(b,HIGH);
  digitalWrite(c,HIGH);
  digitalWrite(d,LOW);
  digitalWrite(e,LOW);
  digitalWrite(f,LOW);
  digitalWrite(g,LOW);
}
void eight()
{
  digitalWrite(a,HIGH);
  digitalWrite(b,HIGH);
  digitalWrite(c,HIGH);
  digitalWrite(d,HIGH);
  digitalWrite(e,HIGH);
  digitalWrite(f,HIGH);
  digitalWrite(g,HIGH);
}
void nine()
{
  digitalWrite(a,HIGH);
  digitalWrite(b,HIGH);
  digitalWrite(c,HIGH);
  digitalWrite(d,HIGH);
  digitalWrite(e,LOW);
  digitalWrite(f,HIGH);
  digitalWrite(g,HIGH);
}
```
### Working Video
#### Virtual Simulation
[![Digital dice](https://user-images.githubusercontent.com/42141371/147594549-f0fd04db-4021-4392-a5e3-55f934bdce98.png)](https://user-images.githubusercontent.com/42141371/159980008-dc85517a-7bac-4cec-bde0-fc5b5d3115b0.mp4)
#### Actual Simulation
[![Digital dice](https://user-images.githubusercontent.com/42141371/159980171-ab775b06-d087-44d8-829f-d83e8b16cea9.jpg)](https://user-images.githubusercontent.com/42141371/159980461-56f17b56-2aa7-420d-a495-1013db69bc31.mp4)
