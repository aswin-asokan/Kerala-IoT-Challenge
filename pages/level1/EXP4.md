## Experiment 4 : Button Controlled LED
### Description : 
_In this experiment we use a button to control the LED. A Push Button switch is a type of switch which consists of a simple electric mechanism to turn something on or off._   
![button](https://user-images.githubusercontent.com/86108610/148683754-4caa7bcb-245e-4f17-804e-a0b57068be0e.jpeg)

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
_Connections are made according to the Circuit given_   
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
_The output of this experiment would be like this :_   
<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/146938026-f2cbf63e-f626-4e31-9317-972a4cb3313a.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>
