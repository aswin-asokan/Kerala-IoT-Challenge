# Kerala IoT Challenge Level 1
## Table of Contents   
1. [Hello World LED Blinking](#blink)
2. [Traffic Light](#traffic)
3. [LED Chasing Effect](#chase)
4. [Button Controlled LED](#button)
5. [Buzzer](#buzzer)
6. [RGB LED](#rgb)
7. [LDR Light Sensor](#ldr)
8. [Flame Sensor](#flame)
9. [LM35 Temperature Sensor](#lm35)
## Experiment 1 : Hello World LED Blinking<a name="blink"></a>
_This is just a basic arduino experiment to blink a LED with a time interval of 1 second._
### Components Used :   
* Arduino Uno Board
* USB Cable
* LED (Any Color) x 1 Nos
* 220Ω Resistor x 1 Nos
* Breadboard
* Jumper Wires (Male to Male ) x 2 Nos
 
### Circuit Diagram :
![Expriment 1](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/Circuit1.png)

### Code :

```
#define ledpin 10 //define digital pin 10
void setup() { 
  pinMode(ledpin,OUTPUT); //define pin with LED as output
}

void loop() {
  digitalWrite(ledpin,HIGH); //LED on
  delay(1000); //wait for 1 second
  digitalWrite(ledpin,LOW); //LED off
  delay(1000); //wait for 1 second
}
```

### Video :

<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/146636287-d307cc4a-e22b-4290-9088-4a1bad826210.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>

### Experience :   
_Even though it was just a basic experiment I was excited to do it as it was my first ever hands-on experience using Arduino. It was cool and made me more interested in working with it._


## Experiment 2 : Traffic Light<a name="traffic"></a>
_Similar to experiment 1 but here we use 3 LEDs instead of 1 to implement a traffic light_   
### Components Used:
* Arduino board 
* USB cable 
* Red M5 LED x 1
* Yellow M5 LED x 1
* Green M5 LED x 1
* 220Ω resistor x 1 
* Breadboard
* Breadboard jumper wires

### Circut:
![Expriment 2](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/Circuit2.png)

### Code :

```
#define redLED 7 //define digital pin 7
#define yellowLED 5 //define digital pin 5
#define greenLED 3 //define digital pin 3
void setup()
{
  pinMode(redLED, OUTPUT); //define pin with red LED as output
  pinMode(yellowLED, OUTPUT); //define pin with yellow as output
  pinMode(greenLED, OUTPUT); //define pin with green LED as output
}

void loop()
{
  //turn on red LED wait for 5 second
  digitalWrite(redLED, HIGH);
  delay(5000);
  digitalWrite(redLED, LOW);//turn off red LED
  for(int i=0;i<3;i++) //blink yellow LED for 3 times
  {
    delay(500); //wait for 0.5 second
    //turn on yellow LED and wait for 0.5 second
    digitalWrite(yellowLED, HIGH);
    delay(500);
    digitalWrite(yellowLED, LOW); //turn off yellow LED
  }
  delay(500); //wait for 0.5 second
  //turn on green LED wait for 5 second
  digitalWrite(greenLED, HIGH);
  delay(5000);
  digitalWrite(greenLED, LOW);//turn off green LED
}
```
### Video :

<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/146650467-6e154c1d-a4ce-4963-b868-7a61ae89ded7.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>


## Experiment 3 : LED Chasing Effect<a name="chase"></a>
_In this experiment we create a program to simulate LED chasing effect_
### Components Used :   
* LED Green x 3
* LED Red x 3
* Arduino board 
* 220Ω resistor x 2
* Breadboard 
* USB cable
* Breadboard jumper wires

### Circuit :
![Expriment 3](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/Circuit3.png)

### Code :

```
#define BASE 2 //define pin 2 as I/O for first LED
#define NUM 6 // number of LEDs
void setup()
{
  for(int i = BASE;i < BASE + NUM;i++)
  {
    pinMode(i, OUTPUT); //set I/O pins as Output
  }
}
void loop()
{
  for(int i = BASE;i < BASE + NUM;i++)
  {
    digitalWrite(i, LOW); //turn off LEDs 1 by 1
    delay(200); //wait for 0.2 second
  }
  for(int i = BASE;i < BASE + NUM;i++)
  {
    digitalWrite(i, HIGH); //turn on LEDs 1 by 1
    delay(200); //wait for 0.2 second
  }
}
```
### Video :

<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/146650723-146145fe-2956-4c80-bba8-c3832f78bdc2.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>

### Experience :
_Tried to reduce the number of resistors used and I think it made the wiring a bit complicated. Eventhough it worked without any issues_

## Experiment 4 : Button Controlled LED<a name="button"></a>
_In this experiment we use a button to control the LED_
### Components Used :   
* Arduino Uno
* Button switch x 1
* Red M5 LED x 1
* 220Ω Resistor x 1
* 10KΩ Resistor x 1
* Breadboard x 1
* Breadboard Jumper Wire x 5
* USB cable x 1

### Circuit :
![Expriment 4](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/Circuit4.png)

### Code :

```
#define ledpin 11 // initialize pin 11
#define  inpin 6 // initialize pin 6
int val;// define val
void setup()
{
pinMode(ledpin,OUTPUT);// set LED pin as “output”
pinMode(inpin,INPUT);// set button pin as “input”
}
void loop()
{
val=digitalRead(inpin);// read the level value of pin 7 and assign if to val
if(val==LOW)// check if the button is pressed, if yes, turn on the LED
{ 
  digitalWrite(ledpin,LOW);
}
else
{ 
  digitalWrite(ledpin,HIGH);
}
}
```
### Video :

<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/146938026-f2cbf63e-f626-4e31-9317-972a4cb3313a.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>

## Experiment 5 : Buzzer<a name="buzzer"></a>
_This experiment is done inorder to understand the functioning of a buzzer using Arduino_
### Components Used :   
* Arduino Uno
* Buzzer x 1
* Breadboard x 1
* Breadboard Jumper Wire x 2
* USB cable x 1

### Circuit :   
![Expriment 5](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/Circuit5.png)

### Code :

```
#define BUZZER 10
void setup() 
{
  pinMode(BUZZER, OUTPUT);
}

void loop() 
{
  digitalWrite(BUZZER, HIGH);
}
```

### Video :

<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/147457180-3af26922-6c1f-4e46-8603-72dd087804b1.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>

## Experiment 6 : RGB LED<a name="rgb"></a>
_An RGB LED bulb uses three diodes in Red, Green and Blue. These are mixed in different intensities to produce a variety of different colours. As mentioned earlier, RGB LEDs have three LEDs inside them and usually, these three internal LEDs share either a common anode or a common cathode especially in a through-hole package. So basically, we can categorize RGB LEDs as either common anode or common cathode type just like in seven segment displays. When you look at an RGB LED, you'll see that it has four leads. If you face it so that its longest lead is second from the left, the leads should be in the following order: red, anode or cathode, green, and blue._

![RGB](https://github.com/aswin-asokan/Kerala-IoT-Challenge/blob/gh-pages/files/level1/images/RGB-LEDs-Pinout.png)

_This experiment is done to produce different colours using RGB LED._
### Components Used :   
* Arduino Uno
* USB Cable x 1
* RGB LED x 1
* Resistor x 3
* Breadboard jumper wire x 5

### Circuit :
![Expriment 6](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/Circuit6.png)

### Code :
```
int red = 11; //select the pin for the red LED
int green =10;// select the pin for the green LED
int blue =9; // select the pin for the blue LED
int val;
void setup() {
  pinMode(red, OUTPUT);
  pinMode(blue, OUTPUT);
  pinMode(green, OUTPUT);
  Serial.begin(9600);
}
void loop() 
{
for(val=255; val>0; val--)
  {
   analogWrite(red, val);
   analogWrite(green, 255-val);
   analogWrite(blue, 128-val);
   delay(1); 
  }
for(val=0; val<255; val++)
  {
   analogWrite(red, val);
   analogWrite(green, 255-val);
   analogWrite(blue, 128-val);
   delay(1); 
  }
 Serial.println(val, DEC);
 ```
 
### Video :

<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/147458241-92faf061-572e-49bf-b704-1700ba4e9959.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>

## Experiment 7 : LDR Light Sensor<a name="ldr"></a>
_LDRs (light-dependent resistors) are used to detect light levels, for example, in automatic security lights. Their resistance decreases as the light intensity increases: in the dark and at low light levels, the resistance of an LDR is high and little current can flow through it. Here we use a LDR sensor to detect light and make a LED work according to the data got from the sensor._

### Components Used :
* Arduino Uno Board
* Photo Resistor x 1
* Green M5 LED x 1
* 10KΩ Resistor x 1
* 220Ω Resistor x 1
* Breadboard x 1
* Breadboard Jumper Wire x 5
* USB cable x 1

### Circuit :
![Expriment 7](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/Circuit7.png)

### Code :
```
int potpin=0;// initialize analog pin 0, connected with photovaristor
int ledpin=11;// initialize digital pin 11, 
int val=0;// initialize variable val
void setup()
{
pinMode(ledpin,OUTPUT);// set digital pin 11 as “output”
Serial.begin(9600);// set baud rate at “9600”
}
void loop()
{
val=analogRead(potpin);// read the value of the sensor and assign it to val
Serial.println(val);// display the value of val
analogWrite(ledpin,val/4);// set up brightness（maximum value 255）
delay(10);// wait for 0.01 
}
```

### Video :
<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/147466800-e9d8d7ce-91c4-4cbe-a895-921e4d9c2189.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>

## Experiment 8 : Flame Sensor<a name="flame"></a>
_Here we use an Infrared Receiver (IR) to detect flame. A buzzer is included to make sound in case of flame._

### Components Used :
* Arduino Uno Board
* Flame Sensor x 1
* Buzzer x 1
* 10KΩ Resistor x 1
* Breadboard Jumper Wire x 6
* USB cable x 1

### Circuit : 
![Expriment 8](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/Circuit8.png)

### Code : 

```
int flame=0;// select analog pin 0 for the sensor
int Beep=9;// select digital pin 9 for the buzzer
int val=0;// initialize variable
 void setup() 
{
  pinMode(Beep,OUTPUT);// set LED pin as “output”
 pinMode(flame,INPUT);// set buzzer pin as “input”
 Serial.begin(9600);// set baud rate at “9600”
 } 
void loop() 
{ 
  val=analogRead(flame);// read the analog value of the sensor 
  Serial.println(val);// output and display the analog value
  if(val>=600)// when the analog value is larger than 600, the buzzer will buzz
  {  
    digitalWrite(Beep,HIGH); 
  }
  else 
  {  
    digitalWrite(Beep,LOW); 
  }
   delay(500); 
}
```

### Video :

<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/147467357-d8e205d2-56ba-45c9-be55-bee62b6ac1fc.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>

## Experiment 9 : LM35 Temperature Sensor<a name="lm35"></a>
_LM35 is a type of commonly used temperature sensor, that can be used to measure temperature with an electrical output comparative to the temperature in (°C). It can measure temperature in a better way than thermistor. It has an accuracy of ±1/4°C. The output temperature is 0℃～100℃, the conversion formula is as follows:_   

![Equation](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/equation.png)

#### LM35 fig :
![LM35](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/lm35.png)
<table>
  <tr>
    <th>Pin Number</th>
    <th>Pin Name</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>1</td>
    <td>Vcc</td>
    <td>Input voltage is +5V for typical applications</td>
  </tr>
  <tr>
    <td>2</td>
    <td>Analog Out</td>
    <td>There will be increase in 10mV for raise of every 1°C. Can range from -1V(-55°C) to 6V(150°C)</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Ground</td>
    <td>Connected to ground of circuit</td>
  </tr>
</table>

### Components Used :
* Arduino Uno  Board
* LM35 x 1
* Breadboard x 1
* Breadboard Jumper Wire x 3
* USB cable

### Circuit :
![LM35](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/Circuit9.png)

### Code :

```
int potPin = 0; // initialize analog pin 0 for LM35 temperature sensor
void setup()
{
Serial.begin(9600);// set baud rate at”9600”
}
void loop()
{
int val;// define variable
int dat;// define variable
val=analogRead(0);// read the analog value of the sensor and assign it to val
dat=(125*val)>>8;// temperature calculation formula
Serial.print("Temperature = ");// output and display characters beginning with "Temperature ="
Serial.print(dat);// output and display value of dat
Serial.println("°C");// display “°C” characters
delay(500);// wait for 0.5 second
}
```

### Pictures : 
_Connected Circuit :_   
![circuit](https://github.com/aswin-asokan/Kerala-IoT-Challenge/blob/gh-pages/files/level1/images/EXP9.jpg)
_Serial Monitor Output :_    
![Output](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/EXP9.png)
