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
void setup() { 
  pinMode(ledpin,OUTPUT);
}

void loop() {
  digitalWrite(ledpin,HIGH);
  delay(1000);
  digitalWrite(ledpin,LOW);
  delay(1000);
}
```

### Video :

<iframe min-width="320" min-height="240" max-width="854" max-height="480"
src="https://user-images.githubusercontent.com/86108610/146636287-d307cc4a-e22b-4290-9088-4a1bad826210.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>

### Experience :   
_Even though it was just a basic experiment I was excited to do it as it was my first ever hands-on experience using Arduino. It was cool and made me more interested in working with it._
