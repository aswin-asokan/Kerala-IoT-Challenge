## Experiment 3 : LED Chasing Effect
### Description :
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
_Connections are made according to the Circuit given_   
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
_The output of this experiment would be like this :_   
<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/147735511-5619be74-e8d5-4cbb-a545-58224536b7e1.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>
