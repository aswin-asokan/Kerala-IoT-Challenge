# Kerala IoT Challenge Level 1
## Table of Contents   
1. [Hello World LED Blinking](#blink)
2. [Traffic Light](#traffic)
3. [LED Chasing Effect](#chase)
4. [Button Controlled LED](#button)
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
