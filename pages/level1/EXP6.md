## Experiment 6 : RGB LED
### Description :   
_An RGB LED bulb uses three diodes in Red, Green and Blue. These are mixed in different intensities to produce a variety of different colours. As mentioned earlier, RGB LEDs have three LEDs inside them and usually, these three internal LEDs share either a common anode or a common cathode especially in a through-hole package. So basically, we can categorize RGB LEDs as either common anode or common cathode type just like in seven segment displays. When you look at an RGB LED, you'll see that it has four leads. If you face it so that its longest lead is second from the left, the leads should be in the following order: red, anode or cathode, green, and blue._

![RGB-LEDs-Pinout](https://user-images.githubusercontent.com/86108610/147626886-f1b4e030-0de5-4363-a1f1-65b264914e83.png)

_This experiment is done to produce different colours using RGB LED._
### Components Used :   
* Arduino Uno
* USB Cable x 1
* RGB LED x 1
* Resistor x 3
* Breadboard jumper wire x 5

### Circuit :
_Connections are made according to the Circuit given_   
![Expriment 6](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/Circuit6.png)

### Code :
```
int red = 11; //select the pin for the red LED
int green =10;// select the pin for the green LED
int blue =9; // select the pin for the blue LED
int val;
void setup() {
  pinMode(red, OUTPUT);
  pinMode(blue, OUTPUT);
  pinMode(green, OUTPUT);
}
void loop() 
{
for(val=255; val>0; val--)
  {
   analogWrite(red, val);
   analogWrite(green, 255-val);
   analogWrite(blue, 128-val);
   delay(1); 
  }
for(val=0; val<255; val++)
  {
   analogWrite(red, val);
   analogWrite(green, 255-val);
   analogWrite(blue, 128-val);
   delay(1); 
  }
}
 ```
 
### Video :
_The output of this experiment would be like this :_   
<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/147458241-92faf061-572e-49bf-b704-1700ba4e9959.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>
