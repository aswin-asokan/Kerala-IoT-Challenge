## Experiment 11 : Potentiometer analog Value Reading
### Description :   
_In this experiment we are reading value(Analog Value) from a Potentiometer and use it to light a LED accordingly. A potentiometer is a three-terminal resistor with a sliding or rotating contact that forms an adjustable voltage divider. It acts as a variable resistor_   
![potentiometer](https://user-images.githubusercontent.com/86108610/147745703-0dd92d81-3967-4485-b06d-a40187044ce7.png)

### Circuit :
_Connections are made according to the Circuit given_   
![circuit](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/Circuit11.png)  

### Code :

```
int potpin=0;
int ledpin=11;
int val=0;
int ledval=0;
void setup()
{
pinMode(ledpin,OUTPUT);
Serial.begin(9600);
}
void loop()
{
val=analogRead(potpin);
Serial.println(val);
ledval=map(val,0,1023,0,255);
analogWrite(ledpin, ledval);
}
```    
_Visit [**map()**](https://www.arduino.cc/reference/en/language/functions/math/map/) to refer more about it._
### Video :
_The output of this experiment would be like this :_ 
<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/147812681-dfb825ae-3455-43f4-8906-28c9af9d4b7f.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>   

_Serial Monitor Output :_  
<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/147812992-6f4937be-8cfa-4506-90a9-894d70c4e837.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>     
