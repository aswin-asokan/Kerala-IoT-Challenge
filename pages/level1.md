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

<iframe width="480px" height="360px"
src="https://user-images.githubusercontent.com/86108610/146636287-d307cc4a-e22b-4290-9088-4a1bad826210.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>

### Experience :   
_Even though it was just a basic experiment I was excited to do it as it was my first ever hands-on experience using Arduino. It was cool and made me more interested in working with it._


### Experiment 2 : Traffic Light
_Similar to experiment 1 but here we use 3 LEDs instead of 1 to implement a traffic light_   
### Components Required:
* Arduino board *1
* USB cable *1
* Red M5 LED*1
* Yellow M5 LED*1
* Green M5 LED*1
* 220Ω resistor*1 
* Breadboard*1
* Breadboard jumper wires
### Circut:
![Expriment 2](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/Circuit2.png)
