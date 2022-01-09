## Experiment 2 : Traffic Light
### Description :   
_Similar to experiment 1 but here we use 3 LEDs instead of 1 to implement a traffic light. Visit experiment 1 for doubts regarding LED or Resistor_   
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
_Connections are made according to the Circuit given_   
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
_The output of this experiment would be like this :_   
<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/146650467-6e154c1d-a4ce-4963-b868-7a61ae89ded7.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>
