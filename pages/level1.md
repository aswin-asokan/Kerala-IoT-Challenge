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
10. [IR Remote Control Using TSOP](#remote)
11.  [Potentiometer analog Value Reading](#potentiometer)
12.  [7 Segment Display](#segment)
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

_Even though it was just a basic experiment I was excited to do it as it was my first ever hands-on experience using Arduino. It was cool and made me more interested in working with it._   

## Experiment 2 : Traffic Light<a name="traffic"></a>
_Similar to experiment 1 but here we use 3 LEDs instead of 1 to implement a traffic light_   
### Components Used:
* Arduino board 
* USB cable 
* LED Green x 1
* LED Yellow x 1
* LED Red x 1
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
* LED Green x 2
* LED Yellow x 2
* LED Red x 2
* Arduino board 
* 220Ω resistor x 6
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
src="https://user-images.githubusercontent.com/86108610/147735511-5619be74-e8d5-4cbb-a545-58224536b7e1.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>

## Experiment 4 : Button Controlled LED<a name="button"></a>
_In this experiment we use a button to control the LED_
### Components Used :   
* Arduino Uno
* Button switch x 1
* LED Red x 1
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

![RGB-LEDs-Pinout](https://user-images.githubusercontent.com/86108610/147626886-f1b4e030-0de5-4363-a1f1-65b264914e83.png)

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
* LED Green x 1
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
![EXP9](https://user-images.githubusercontent.com/86108610/147627049-75d8a992-dcad-41c2-a1ab-1e9642c02404.png)

_Serial Monitor Output :_    
![Output](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/EXP9.png)

## Experiment 10 : IR Remote Control Using TSOP<a name="remote"></a>

_An IR receiver can detect bursts of infrared light sent by a common remote controller (like for a television), and then output a pattern of high/low signals to a Propeller I/O pin. In this experiment we use a IR receiver to identify and respond to a remote_
### Pin Diagram :   
![diagram](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/ir.png)   
_First we need to decode the IR remote codes. For this the given circuit is created and required remote codes are acquired from the serial monitor_   
#### Components Used
* Arduino Uno Board
* Infrared Remote Controller(TV Remote or any other remote) 
* Infrared Receiver x 1
* Breadboard Wire x 3
* USB cable
#### Circuit :
![circuit](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/Circuit10a.png)   
#### Code :

```
#include<IRremote.h>
const int RECV_PIN = 12;
IRrecv irrecv(RECV_PIN);
decode_results results;
void setup() 
{
  Serial.begin(9600);
  irrecv.enableIRIn();
}

void loop() 
{
  if(irrecv.decode(&results))
  {
    Serial.println(results.value,HEX);
    irrecv.resume();
  }
}
```
   
#### Serial Monitor Output :
![circuit](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/serial.png)   
_Ignore the FFFFFFFF   
Now coming back to the experiment_

### Components Used :
* Arduino Uno Board
* Infrared Remote Controller(TV Remote or any other remote) 
* Infrared Receiver 1
* LED Green x 2
* LED Yellow x 2
* LED Red x 2
* 220Ω Resistor x 6
* Breadboard Wire x 10
* USB cable

### Circuit :
![Circuit10](https://user-images.githubusercontent.com/86108610/147741039-9560fbb9-42db-4cf3-b7a4-507b1206c2ce.png)

### Code :

```
#include<IRremote.h>
const int RECV_PIN = 12;
int LED[6]={7,6,5,4,3,2};
int togglestate[6]={0,0,0,0,0,0};
long remote[6]={0x1FE50AF,0x1FED827,0x1FEF807,0x1FE30CF,0x1FEB04F,0x1FE708F};//change the values with codes yo got from your remote
int i;
IRrecv irrecv(RECV_PIN);
decode_results results;
void setup()
{
  irrecv.enableIRIn();
  for(i=0;i<6;i++)
  {
    pinMode(LED[i],OUTPUT);
  }
}
void loop()
{
  if(irrecv.decode(&results))
  {
    for(i=0;i<6;i++)
    {
      if(results.value==remote[i])
      {
        if(togglestate[i]==0)
        {
          digitalWrite(LED[i],HIGH);
          togglestate[i]=1;
        }
        else
        {
          digitalWrite(LED[i],LOW);
          togglestate[i]=0;
        }
      }
      irrecv.resume();
    }
  }
}
```   
_Refer to this [**Video**](https://www.youtube.com/watch?v=8E3ltjnbV0c) to learn about remote codes. Also, refer the [**Video**](https://www.youtube.com/watch?v=FRhzuWl39qg) by [**Sci-COPATH**](https://www.youtube.com/channel/UCeATKlkbBC8xT7r8hmK26EQ) to understand array._    
### Video :
<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/147742163-87ecdb39-4c5b-4aa9-bdd4-cc77e1cd27f6.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>
   
### Picture :
![EXP10](https://user-images.githubusercontent.com/86108610/147740626-b9ac88f1-97b8-4812-8ed2-44471691a6c3.png)

## Experiment 11 : Potentiometer analog Value Reading<a name="potentiometer"></a>

_In this experiment we are reading value(Analog Value) from a Potentiometer and use it to light a LED accordingly. A potentiometer is a three-terminal resistor with a sliding or rotating contact that forms an adjustable voltage divider. It acts as a variable resistor_   
![potentiometer](https://user-images.githubusercontent.com/86108610/147745703-0dd92d81-3967-4485-b06d-a40187044ce7.png)

### Circuit :
![circuit](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/Circuit11.png)  

### Code :

```
int potpin=0;
int ledpin=11;
int val=0;
int ledval=0;
void setup()
{
pinMode(ledpin,OUTPUT);
Serial.begin(9600);
}
void loop()
{
val=analogRead(potpin);
Serial.println(val);
ledval=map(val,0,1023,0,255);
analogWrite(ledpin, ledval);
}
```    
_Visit [**map()**](https://www.arduino.cc/reference/en/language/functions/math/map/) to refer more about it._
### Video :

<iframe width="352" height="240"
src=""
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>   

_Serial Monitor Output :_  
<iframe width="352" height="240"
src=""
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>   

## Experiment 12 : 7 Segment Display<a name="segment"><a/>
 _LED segment display is a semiconductor light-emitting device. Its basic unit is a light-emitting diode (LED). LED segment display can be divided into 7-segment display and 8-segment display according to the number of segments. 8-segment display has one more LED unit ( for decimal point display) than 7-segment one. In this experiment we use this to display numbers from zero to nine_   
![segment](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/segment.png)   
 
 ### Components :
 
* Arduino Uno Board
* 1-digit LED Segment Display x 1
* 220Ω Resistor x 1
* Breadboard
* Breadboard Jumper Wires x several
* USB cable
 
 ### Circuit :
 ![circuit](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/Circuit12.png)  
 
 ### Code :
 
 ```
 //define each pin
#define A 7
#define B 6
#define C 4
#define D 8
#define E 9
#define F 11
#define G 10
#define DP 5
//display 0
void zero(void)
{
  digitalWrite(A, HIGH);
  digitalWrite(B, HIGH);
  digitalWrite(C, HIGH);
  digitalWrite(D, HIGH);
  digitalWrite(E, HIGH);
  digitalWrite(F, HIGH);
}
void one(void)
{ 
  digitalWrite(B, HIGH);
  digitalWrite(C, HIGH);
}
void two(void)
{
  digitalWrite(A, HIGH);
  digitalWrite(B, HIGH);
  digitalWrite(D, HIGH);
  digitalWrite(E, HIGH);
  digitalWrite(G, HIGH);
}
void three(void)
{
  digitalWrite(A, HIGH);
  digitalWrite(B, HIGH);
  digitalWrite(C, HIGH);
  digitalWrite(D, HIGH);
  digitalWrite(G, HIGH);
}
void four(void)
{
  digitalWrite(B, HIGH);
  digitalWrite(C, HIGH);
  digitalWrite(F, HIGH);
  digitalWrite(G, HIGH);
}
void five(void)
{
  digitalWrite(A, HIGH);
  digitalWrite(C, HIGH);
  digitalWrite(D, HIGH);
  digitalWrite(F, HIGH);
  digitalWrite(G, HIGH);
}
void six(void)
{
  digitalWrite(A, HIGH);
  digitalWrite(C, HIGH);
  digitalWrite(D, HIGH);
  digitalWrite(E, HIGH);
  digitalWrite(F, HIGH);
  digitalWrite(G, HIGH);
}
void seven(void)
{
  digitalWrite(A, HIGH);
  digitalWrite(B, HIGH);
  digitalWrite(C, HIGH);
}
void eight(void)
{
  digitalWrite(A, HIGH);
  digitalWrite(B, HIGH);
  digitalWrite(C, HIGH);
  digitalWrite(D, HIGH);
  digitalWrite(E, HIGH);
  digitalWrite(F, HIGH);
  digitalWrite(G, HIGH);
}
void nine(void)
{
  digitalWrite(A, HIGH);
  digitalWrite(B, HIGH);
  digitalWrite(C, HIGH);
  digitalWrite(D, HIGH);
  digitalWrite(F, HIGH);
  digitalWrite(G, HIGH);
}
void clear(void)
{
  digitalWrite(A, LOW);
  digitalWrite(B, LOW);
  digitalWrite(C, LOW);
  digitalWrite(D, LOW);
  digitalWrite(E, LOW);
  digitalWrite(F, LOW);
  digitalWrite(G, LOW);
  digitalWrite(DP, LOW);
}
void setup()
{
  for(int i=4;i<=11;i++)
  {
    pinMode(i, OUTPUT);
  }
}
void loop()
{
  clear();
  zero();
  delay(1000);
  clear();
  one();
  delay(1000);
  clear();
  two();
  delay(1000);
  clear();
  three();
  delay(1000);
  clear();
  four();
  delay(1000);
  clear();
  five();
  delay(1000);
  clear();
  six();
  delay(1000);
  clear();
  seven();
  delay(1000);
  clear();
  eight();
  delay(1000);
  clear();
  nine();
  delay(1000);
}
```
                        
