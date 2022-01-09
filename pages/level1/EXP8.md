## Experiment 8 : Flame Sensor
### Description :   
_Here we use an Infrared Receiver (IR) to detect flame. A buzzer is included to make sound in case of flame._   
![Flame](https://user-images.githubusercontent.com/86108610/148689366-82df06c5-085e-4860-a2eb-5b662c01df92.png)


### Components Used :
* Arduino Uno Board
* Flame Sensor x 1
* Buzzer x 1
* 10KΩ Resistor x 1
* Breadboard Jumper Wire x 6
* USB cable x 1

### Circuit :   
_Connections are made according to the Circuit given_   
![Expriment 8](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/Circuit8.png)

### Code : 

```
int flame=0;// select analog pin 0 for the sensor
int Beep=9;// select digital pin 9 for the buzzer
int val=0;// initialize variable
 void setup() 
{
  pinMode(Beep,OUTPUT);// set LED pin as “output”
 pinMode(flame,INPUT);// set buzzer pin as “input”
 Serial.begin(9600);// set baud rate at “9600”
 } 
void loop() 
{ 
  val=analogRead(flame);// read the analog value of the sensor 
  Serial.println(val);// output and display the analog value
  if(val>=600)// when the analog value is larger than 600, the buzzer will buzz
  {  
    digitalWrite(Beep,HIGH); 
  }
  else 
  {  
    digitalWrite(Beep,LOW); 
  }
   delay(500); 
}
```

### Video :   
_The output of this experiment would be like this :_   
<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/147467357-d8e205d2-56ba-45c9-be55-bee62b6ac1fc.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>
