# Kerala IoT Challenge Level 1
## Experiment 1 : Hello World LED Blinking
_This is just a basic arduino experiment to blink a LED with a time interval of 1 second._
### Components Required :   
* Arduino Uno Board
* USB Cable
* LED (Any Color) x 1 Nos
* 220 OHM Resistor x 1 Nos
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
