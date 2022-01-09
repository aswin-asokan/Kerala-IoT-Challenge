## <a name="lm35"></a>Experiment 9 : LM35 Temperature Sensor
### Description :   
_LM35 is a type of commonly used temperature sensor, that can be used to measure temperature with an electrical output comparative to the temperature in (°C). It can measure temperature in a better way than thermistor. It has an accuracy of ±1/4°C. The output temperature is 0℃～100℃, the conversion formula is as follows:_   

![Equation](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/equation.png)

#### LM35 fig :
![LM35](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/lm35.png)
<table>
  <tr>
    <th>Pin Number</th>
    <th>Pin Name</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>1</td>
    <td>Vcc</td>
    <td>Input voltage is +5V for typical applications</td>
  </tr>
  <tr>
    <td>2</td>
    <td>Analog Out</td>
    <td>There will be increase in 10mV for raise of every 1°C. Can range from -1V(-55°C) to 6V(150°C)</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Ground</td>
    <td>Connected to ground of circuit</td>
  </tr>
</table>

### Components Used :
* Arduino Uno  Board
* LM35 x 1
* Breadboard x 1
* Breadboard Jumper Wire x 3
* USB cable

### Circuit :   
_Connections are made according to the Circuit given_   
![LM35](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/Circuit9.png)

### Code :

```
int potPin = 0; // initialize analog pin 0 for LM35 temperature sensor
void setup()
{
Serial.begin(9600);// set baud rate at”9600”
}
void loop()
{
int val;// define variable
int dat;// define variable
val=analogRead(0);// read the analog value of the sensor and assign it to val
dat=(125*val)>>8;// temperature calculation formula
Serial.print("Temperature = ");// output and display characters beginning with "Temperature ="
Serial.print(dat);// output and display value of dat
Serial.println("°C");// display “°C” characters
delay(500);// wait for 0.5 second
}
```

### Pictures : 
_Connected Circuit :_   
![EXP9](https://user-images.githubusercontent.com/86108610/147627049-75d8a992-dcad-41c2-a1ab-1e9642c02404.png)

_Serial Monitor Output :_    
![Output](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/EXP9.png)
