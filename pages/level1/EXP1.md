## Experiment 1 : Hello World LED Blinking
### Description :
_This is just a basic arduino experiment to blink a LED with a time interval of 1 second.   
A __Light-Emitting Diode (LED)__ is a semiconductor light source that emits light when current flows through it._   
![LED_Diagram](https://user-images.githubusercontent.com/86108610/148680290-045184e5-57a9-4d54-a213-93f8c1fb2913.png)   
_Like in the figure, longer leg is the positive side and the shorter leg is the negative side of the LED(Connect according to this in the circuit)._   

_A __Resistor__ is a [passive electrical component](https://en.wikipedia.org/wiki/Electronic_component#Passive_components) with the primary function to limit the flow of electric current._   
<table>
  <tr>
    <th>Color</th>
    <th>Value</th>
    <th>Multiplier</th>
    <th>Tolerence(+ or -)</th>
  </tr>
  <tr>
    <td>Black</td>
    <td>0</td>
    <td>x10<sup>0</sup></td>
    <td>-</td>
  </tr>
  <tr>
    <td>Brown</td>
    <td>1</td>
    <td>x10<sup>1</sup></td>
    <td>1%</td>
  </tr>
  <tr>
    <td>Red</td>
    <td>2</td>
    <td>x10<sup>2</sup></td>
    <td>2%</td>
  </tr>
  <tr>
    <td>Orange</td>
    <td>3</td>
    <td>x10<sup>3</sup></td>
    <td>-</td>
  </tr>
  <tr>
    <td>Yellow</td>
    <td>4</td>
    <td>x10<sup>4</sup></td>
    <td>-</td>
  </tr>
  <tr>
    <td>Green</td>
    <td>5</td>
    <td>x10<sup>5</sup></td>
    <td>0.5%</td>
  </tr>
  <tr>
    <td>Blue</td>
    <td>6</td>
    <td>x10<sup>6</sup></td>
    <td>0.25%</td>
  </tr>
  <tr>
    <td>Violet</td>
    <td>7</td>
    <td>x10<sup>7</sup></td>
    <td>0.10%</td>
  </tr>
  <tr>
    <td>Gray</td>
    <td>8</td>
    <td>x10<sup>8</sup></td>
    <td>0.05%</td>
  </tr>
  <tr>
    <td>White</td>
    <td>9</td>
    <td>x10<sup>9</sup></td>
    <td>-</td>
  </tr>
  <tr>
    <td>Gold</td>
    <td>-</td>
    <td>x10<sup>-1</sup></td>
    <td>5%</td>
  </tr>
  <tr>
    <td>Silver</td>
    <td>-</td>
    <td>x10<sup>-2</sup></td>
    <td>10%</td>
  </tr>
</table>    

We should select our resistor according to the colour code. Here we are using a 220Ω Resistor which is a 4 band resistor whose colour code is Red,Red,Brown,Gold. To learn about colour codes visit this [site](https://www.atlearner.com/2019/07/Resistor-color-code.html).   
![resistor](https://user-images.githubusercontent.com/86108610/148681736-b6628684-f545-4799-9964-378c34e6f447.png)

### Components Used :      

* Arduino Uno Board
* USB Cable
* LED (Any Color) x 1 Nos
* 220Ω Resistor x 1 Nos
* Breadboard
* Jumper Wires (Male to Male ) x 2 Nos
 
### Circuit Diagram :
_Connections are made according to the Circuit given_   
![Expriment 1](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/Circuit1.png)

### Code :

```
#define ledpin 10 //define digital pin 10
void setup() { 
  pinMode(ledpin,OUTPUT); //define pin with LED as output
}
void loop() {
  digitalWrite(ledpin,HIGH); //LED on
  delay(1000); //wait for 1 second
  digitalWrite(ledpin,LOW); //LED off
  delay(1000); //wait for 1 second
}
```    
_Upload this code to the arduino._

### Video :
_The output of this experiment would be like this :_   
<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/146636287-d307cc4a-e22b-4290-9088-4a1bad826210.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>   


_Even though it was just a basic experiment I was excited to do it as it was my first ever hands-on experience using Arduino. It was cool and made me more interested in working with it._   
