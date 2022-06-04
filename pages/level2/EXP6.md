## Experiment 6 : Object Detection using IR Sensor

### Description :  
IR sensor can be used for obstacle sensing, color detection(between basic contrasting colors), fire detection, line sensing, etc and also as an encoder sensor. In this experiment we use it to detect objects with both Arduino and ESP32.

### Contents :
1. [With Arduino](#with-arduino)
2. [With ESP32](#with-esp32)   

### With Arduino   

### Components Used :   
* Arduino UNO
* USB cable A to B
* IR Sensor
* LED Red x 1
* 220Ω resistor x 1 
* Breadboard
* Breadboard jumper wires   

### Circut:
_Connections are made according to the Circuit given_   
![WithArduino](https://user-images.githubusercontent.com/86108610/171998632-4b803e2a-9387-47d8-a302-e5f13641b6db.png)   

### Code :

```
int IRSensor = 7;
int LED = 4;
void setup() 
{
  pinMode (IRSensor, INPUT); // sensor pin INPUT
  pinMode(LED,OUTPUT);
  Serial.begin(9600); // open the serial port at 9600 bps:
}

void loop()
{
  int statusSensor = digitalRead (IRSensor);
  
  if (statusSensor == 1)
  {
    Serial.print("No Obstacle/Black Surface\n"); 
    digitalWrite(LED,LOW);
    }
  else
  {
    Serial.print("Obstacle Detected/White Surface\n");
    digitalWrite(LED,HIGH);
    } 
    
}
```   

### Video :
_The output of this experiment would be like this :_   
<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/171999973-4ca0783a-0c94-4d2a-88cc-b2fc057b89b3.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>

Serial Monitor Output :   
<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/171999394-2f74d2a8-3ca3-4183-b90f-3e8a26dbdd2a.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>   

### With ESP32   

### Components Used :   
* ESP32 board
* USB cable 
* IR Sensor
* LED Red x 1
* 220Ω resistor x 1 
* Breadboard
* Breadboard jumper wires   

### Steps :   
### 1 : Create a variable   
* Click on __Add Variable__ and create a variable named **IR**, make it as **String**.     
![IR1](https://user-images.githubusercontent.com/86108610/171999240-126db847-33a8-45ac-8838-c52be8693dd6.png)   
  
### 2 : Code   
* In the __Sketch__ section, enter the code and upload it to the ESP32.   
 
```
#include "thingProperties.h"
#define IRSensor 34 
#define LED 4
void setup() {
  // Initialize serial and wait for port to open:
  Serial.begin(9600);
  pinMode(IRSensor, INPUT); // sensor pin INPUT
  pinMode(LED,OUTPUT);
  // Defined in thingProperties.h
  initProperties();

  // Connect to Arduino IoT Cloud
  ArduinoCloud.begin(ArduinoIoTPreferredConnection);
  
  /*
     The following function allows you to obtain more information
     related to the state of network and IoT Cloud connection and errors
     the higher number the more granular information you’ll get.
     The default is 0 (only errors).
     Maximum is 4
 */
  setDebugMessageLevel(2);
  ArduinoCloud.printDebugInfo();
}

void loop() {
  ArduinoCloud.update();
  int status = digitalRead(IRSensor);
  if(status == 1)
  {
    iR = "No Obstacle/Black Surface";
    digitalWrite(LED,LOW);
  }
  else
  {
    iR = "Obstacle Detected/White Surface";
    digitalWrite(LED,HIGH);
  } 
  
}
void onIRChange()  {
  // Add your code here to act upon IR change
}
```   
   
### 3 : Dashboard   
* Add a messenger widget to the dashboard with variable as **IR**.   
   
### Circuit :   
![WithESP](https://user-images.githubusercontent.com/86108610/171999319-e12b95a0-455f-44b1-b8e8-960d600a40d0.png)   
 
### Working :
![IR](https://user-images.githubusercontent.com/86108610/171999333-44ac0e85-e3c4-4389-8357-d59c5efda428.png)
   

For a detailed instruction visit :   
* [Learn To Operate IR Sensor With Arduino](https://medium.com/deeplift/beginners-guide-to-learning-arduino-technology-b01ab76549e6)
