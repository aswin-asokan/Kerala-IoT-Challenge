# Kerala IoT Challenge Level 1
## Experiment 1 : Hello World LED Blinking
_This is just a basic arduino experiment to blink a LED with a time interval of 1 second._
### Components Required :   
* Arduino Uno Board
* USB Cable
* LED (Any Color) x 1 Nos
* 220 OHM Resistor X 1 Nos
* Breadboard
* Jumper Wires (Male to Male ) X 2 Nos
### Circuit Diagram :
![Expriment 1](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/Circuit1.png)
### Code :   
```
#define ledpin 10
void setup() 
{ 
  pinMode(ledpin,OUTPUT);
}

void loop() 
{
  digitalWrite(ledpin,HIGH);
  delay(1000);
  digitalWrite(ledpin,LOW);
  delay(1000);
}
```

### Video :

https://user-images.githubusercontent.com/86108610/146634813-d5ccfed4-fc31-450e-bf18-4786cc146b18.mp4

### Experience :   
_Even though it was just a basic experiment I was excited to do it as it was my first ever hands-on experience using Arduino. It was cool and made me more interested in working more with it._
