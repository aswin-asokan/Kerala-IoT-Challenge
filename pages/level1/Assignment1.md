## Assignment 1 : Automatic Night Lamp   
### Description :   
 _Here we use a LDR to detect light and use it to make an automatic night lamp which turns on while there is no other light source available_   
 _To learn more about LDR visit [Experiment 7](https://aswin-asokan.github.io/Kerala-IoT-Challenge/pages/level1/EXP7)_
 
### Components and Supplies Used :
 
* Arduino Uno Board
* Photo Resistor x 1
* LED Yellow x 5
* 10KΩ Resistor x 1
* 220Ω Resistor x 5
* Breadboard x 1
* Breadboard Jumper Wire x several
* USB cable x 1
* Cardboard 
* Chart paper
* Masking tape
     
### Circuit :
_Connections are made according to the Circuit given_   
![ASSIGN1 png](https://user-images.githubusercontent.com/86108610/151673822-3ab617d6-5cc9-4dcc-94fb-b0669a885730.png)


### Construction of lamp :
For the construction of body for the lamp, download and go through this PDF :   
[Construction.pdf](https://github.com/aswin-asokan/Kerala-IoT-Challenge/files/7965454/Construction.pdf)



### Code :
 
 ```
int  photocellPin = 0;
int led[5] = {7,6,5,4,3};
int val = 0;
int i;
const int limit = 280;
void setup(void)
{
  for(i=0;i<5;i++)
  {
    pinMode(led[i],OUTPUT);
  }
Serial.begin(9600);
}
void loop(void)
{
val = analogRead(photocellPin);
if (val > limit)
{
  Serial.println(val);
  for(i=0;i<5;i++)
  {
    digitalWrite(led[i],HIGH);
  }
}
else
{
  for(i=0;i<5;i++)
  {
    digitalWrite(led[i],LOW);
  }
}
}
```                      
### Video :

_The output of this experiment would be like this :_                          
<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/151673642-891aa520-1beb-462d-9e80-8eb41463f02b.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>      

_Double click to view in full screen._
