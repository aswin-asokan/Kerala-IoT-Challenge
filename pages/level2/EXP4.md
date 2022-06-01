## Experiment 4 : Soil Moisture Meter

### Description :  
This is a similar experiment as the previous one. Here we use a soil moisture sensor and display the value using Arduino cloud. Soil Moisture Sensor gives moisture level data using analog pins.     

### Components Used :   
* ESP 32 board
* USB cable 
* Soil moisture sensor
* Female to female jumper wires

### Steps :   
### 1 : Create a variable   
* Click on __Add Variable__ and create a variable named **sm_sensor**, make it as **integer** with **read only** variable permission as we are only taking inputs.     
![soilmoisture](https://user-images.githubusercontent.com/86108610/171215541-328e0a9b-2a62-486d-a202-ec11fc4939c9.png)   

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
    sm_sensor=val;
    Serial.println(val);
  }
```   
   
### 3 : Dashboard   
* Add a guage and chart to the dashboard with variable as **sm_sensor**.   
  ![Screenshot from 2022-05-31 18-17-50](https://user-images.githubusercontent.com/86108610/171213116-55833af2-4a2c-464e-b1bc-5eb75b0bb433.png)   

### Circuit :   

![EXP4](https://user-images.githubusercontent.com/86108610/171215884-6145745f-f4c3-4780-bf93-89c73984a5f9.png)   
![IMG_20220531_175019_tigr-min](https://user-images.githubusercontent.com/86108610/171217227-bd138839-98e1-4c0b-b8e6-57ccaeb08dac.jpg)   


### Working :
<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/171215807-ee8b6d4f-310a-4eba-a52f-adfed576baff.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>  
