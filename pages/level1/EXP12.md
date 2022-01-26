## Experiment 12 : 7 Segment Display
### Description :   
 _LED segment display is a semiconductor light-emitting device. Its basic unit is a light-emitting diode (LED). LED segment display can be divided into 7-segment display and 8-segment display according to the number of segments. 8-segment display has one more LED unit ( for decimal point display) than 7-segment one. In this experiment we use this to display numbers from zero to nine_   
![segment](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/segment.png)   
 
### Components :
 
* Arduino Uno Board
* 1-digit LED Segment Display x 1
* 220Ω Resistor x 8
* Breadboard
* Breadboard Jumper Wires x several
* USB cable
 
### Circuit :
_Connections are made according to the Circuit given_   
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
__The working is simple, we can set functions for each digit, like to display 1 we made function one(). 
As we only need to turn b and c part of segment display on to display 1 we made them to be high and the others will be low.
We made functions for each numbers and set which segments should be on and off in order to display that number.
A clear() function is included to turn off all parts after each digit, just like clear display to show the next digit.__
                        
### Video :

_The output of this experiment would be like this :_                          
<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/147813069-6b1cde88-e364-41bc-8c6b-3a0502be1fb7.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe> 
