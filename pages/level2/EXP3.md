## Experiment 3 : IoT Remote Light Meter using Arduino IoT Cloud

### Description :  
In this experiment we are using LDR and Arduino IoT Cloud , Sending Value from light sensor to Arduino IoT Cloud and display value in dashboard.   

### Components Used :   
* ESP 32 board
* USB cable 
* LDR sensor module
* Female to female jumper wires

### Steps :   
### 1 : Create a variable   
* Click on __Add Variable__ and create a variable named **light_sensor**, make it as **light** with **read only** variable permission as we are only taking inputs.     
![ldr](https://user-images.githubusercontent.com/86108610/171178273-bbef60a8-de71-4fee-9430-ea120a161847.png)   

### 2 : Code   
* In the __Sketch__ section, enter the code and upload it to the ESP32.   
```
  #include "thingProperties.h"
  #define sensor 34
  void setup() {
    Serial.begin(9600);
    delay(1500); 
    pinMode(sensor,INPUT);
    initProperties();
    ArduinoCloud.begin(ArduinoIoTPreferredConnection);
    setDebugMessageLevel(2);
    ArduinoCloud.printDebugInfo();
  }

  void loop() {
    ArduinoCloud.update();
    int val=analogRead(sensor);
    light_sensor=val;
    Serial.println(val);
  }
```   

### 3 : Dashboard   
* Add a guage and chart to the dashboard with variable as **light_sensor**.   
  ![Screenshot from 2022-05-31 18-17-50](https://user-images.githubusercontent.com/86108610/171213116-55833af2-4a2c-464e-b1bc-5eb75b0bb433.png)

### Circuit :   

![EXP3](https://user-images.githubusercontent.com/86108610/171213569-7c611662-11d2-4d23-819a-437fda84e3c6.png)
![IMG_20220531_175110_tigr-min](https://user-images.githubusercontent.com/86108610/171218870-2206e723-b338-4a60-b574-43fd8746252b.jpg)   

### Working :
<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/171213929-fa1c1207-f382-4218-85eb-daf342bc58d7.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>  
