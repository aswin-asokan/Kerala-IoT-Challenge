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


__In Arduino 1023 corresponds to 5V.   
Also 1V gives us 100 celcius. Hence, 5V gives 500 celcius.   
Suppose we take 60 as the value from the sensor temperature will be Temperature = (60 * 500)/1023 = 29.32°C.   
So equation will be Temperature = (value * 500)/1023__   
_Refer this [video](https://www.youtube.com/watch?v=k099LBmwcgE) to learn more about LM35 sensor._   

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
#define TEMP A0
int val;
float temp;
void setup()
{
  pinMode(TEMP,INPUT);
  Serial.begin(9600);
}
void loop()
{
  val=analogRead(TEMP);
  temp=(val*500)/1023;//equation for finding temperature
  Serial.print("Temperature = ");//prints Temperature =
  Serial.print(temp);//prints value of temperature
  Serial.println("°C");//prints °C
  delay(1000);//pause for 1 second
}
```

### Pictures : 
_Connected Circuit :_   
![EXP9](https://user-images.githubusercontent.com/86108610/147627049-75d8a992-dcad-41c2-a1ab-1e9642c02404.png)

_Serial Monitor Output :_    
![Serial](https://user-images.githubusercontent.com/86108610/148737262-9ae9db30-83d3-4612-949e-853c02a327b4.png)

