## Assignment 2 : Digital Dice   
### Description :   
 _Digital dice is made to display numbers from 1 to 6 in a random manner. Here we use a 7 segment display the number and a push button to control it.    
 To learn more about push button visit __[Experiment 4](https://aswin-asokan.github.io/Kerala-IoT-Challenge/pages/level1/EXP4)__   
 To learn more about 7 segment display visit __[Experiment 12](https://aswin-asokan.github.io/Kerala-IoT-Challenge/pages/level1/EXP12)___
 
 
### Components Used :
 
* Arduino Uno Board
* Push button
* 1-digit LED Segment Display x 1
* 220Ω Resistor x 8
* 10KΩ Resistor x 1
* Breadboard
* Breadboard Jumper Wires x several
* USB cable
 
### Circuit :
_Connections are made according to the Circuit given_   
![assign2](https://user-images.githubusercontent.com/86108610/151196947-33d95b9a-ab45-4ef6-ba5d-5347660167be.png)



### Code :
 
 ```
 #define button 2
#define A 7
#define B 6
#define C 4
#define D 8
#define E 9
#define F 11
#define G 10
#define DP 5
int val=0;
int num;
void setup()
{
  pinMode(button,INPUT);
  for(int i=4;i<=11;i++)
  {
    pinMode(i, OUTPUT);
  }
}
void loop()
{
  val=digitalRead(button);
  if(val==HIGH)
  {
    switch(num=random(1,7))
    {
      case 1:
        digitalWrite(A, LOW);
        digitalWrite(B, HIGH);
        digitalWrite(C, HIGH);
        digitalWrite(D, LOW);
        digitalWrite(E, LOW);
        digitalWrite(F, LOW);
        digitalWrite(G, LOW);
        digitalWrite(DP, LOW);
        delay(1000);
        break;
      case 2:
        digitalWrite(A, HIGH);
        digitalWrite(B, HIGH);
        digitalWrite(C, LOW);
        digitalWrite(D, HIGH);
        digitalWrite(E, HIGH);
        digitalWrite(F, LOW);
        digitalWrite(G, HIGH);
        digitalWrite(DP, LOW);
        delay(1000);
        break;
      case 3:
        digitalWrite(A, HIGH);
        digitalWrite(B, HIGH);
        digitalWrite(C, HIGH);
        digitalWrite(D, HIGH);
        digitalWrite(E, LOW);
        digitalWrite(F, LOW);
        digitalWrite(G, HIGH);
        digitalWrite(DP, LOW);
        delay(1000);
        break;
      case 4:
        digitalWrite(A, LOW);
        digitalWrite(B, HIGH);
        digitalWrite(C, HIGH);
        digitalWrite(D, LOW);
        digitalWrite(E, LOW);
        digitalWrite(F, HIGH);
        digitalWrite(G, HIGH);
        digitalWrite(DP, LOW);
        delay(1000);
        break;
      case 5:
        digitalWrite(A, HIGH);
        digitalWrite(B, LOW);
        digitalWrite(C, HIGH);
        digitalWrite(D, HIGH);
        digitalWrite(E, LOW);
        digitalWrite(F, HIGH);
        digitalWrite(G, HIGH);
        digitalWrite(DP, LOW);
        delay(1000);
        break;
      case 6:
        digitalWrite(A, HIGH);
        digitalWrite(B, LOW);
        digitalWrite(C, HIGH);
        digitalWrite(D, HIGH);
        digitalWrite(E, HIGH);
        digitalWrite(F, HIGH);
        digitalWrite(G, HIGH);
        digitalWrite(DP, LOW);
        delay(1000);
        break;
    }
  }
  else
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
}
```   
_Visit [random()](https://www.arduino.cc/reference/en/language/functions/random-numbers/random/) to learn more about the function.   
And visit [Switch](https://www.arduino.cc/reference/en/language/structure/control-structure/switchcase/) to study it's working._   
                        
### Video :

_The output of this experiment would be like this :_                          
<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/151198944-a8291ff5-d3f7-482c-a85f-4156632df5d6.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe> 
