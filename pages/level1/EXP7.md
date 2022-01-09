## <a name="ldr"></a>Experiment 7 : LDR Light Sensor
### Description :   
_LDRs (light-dependent resistors) are used to detect light levels, for example, in automatic security lights. Their resistance decreases as the light intensity increases: in the dark and at low light levels, the resistance of an LDR is high and little current can flow through it. Here we use a LDR sensor to detect light and make a LED work according to the data got from the sensor._   
![LDR](https://user-images.githubusercontent.com/86108610/148685392-6d258f1b-28de-401c-9686-6f0d26154e5d.jpg)



### Components Used :
* Arduino Uno Board
* Photo Resistor x 1
* LED Green x 1
* 10KΩ Resistor x 1
* 220Ω Resistor x 1
* Breadboard x 1
* Breadboard Jumper Wire x 5
* USB cable x 1

### Circuit :
_Connections are made according to the Circuit given_   
![Expriment 7](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/Circuit7.png)

### Code :
```
float  photocellPin = 0;
float ledPin = 11;
float val = 0;
const float limit = 60;
void setup(void)
{
pinMode(ledPin, OUTPUT);
Serial.begin(9600);
}
void loop(void)
{
val = analogRead(photocellPin);
if (val > limit)
{
  Serial.println(val);
  analogWrite(ledPin, val/1.4);
  delay(10);
}
else
{
  digitalWrite(ledPin, LOW);
}
}
```   

_As in the indoor lighting condition the __average minimum value__ from LDR sensor I got was about __60__ and __average maximum value__ was about __355__(from serial monitor). 
Made an if Statement to turn on the LED according to intensity of light while the value was greater than 60 and as the __maximum value for LED is 255, divided value from LDR sensor with 1.4(max=355/1.4=253.7).__
If the statement is false the LED would turn off._
### Video :
_The output of this experiment would be like this :_   
<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/148688608-54deece6-4eac-40ca-8975-df7fd8a17f20.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>




