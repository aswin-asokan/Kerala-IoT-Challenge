## Experiment 5 : Ultrasonic Sensor

### Description :  
In this experiment we create an IoT project that visualize values(Distance in CM)  from an Ultrasonic Sensor in Arduino IoT Dash Board.

### Components Used :   
* ESP 32 board
* USB cable 
* Ultrasonic Sensor
* Breadboard
* Female to male jumper wires

### Steps :   
### 1 : Create a variable   
* Click on __Add Variable__ and create a variable named **cm**, make it as **floating point**  with **read only** variable permission as we are only taking inputs.     
![Sonic4](https://user-images.githubusercontent.com/86108610/171462492-66bac493-a74c-40a8-9f59-ff12739e2763.png)

   
### 2 : Code   
* In the __Sketch__ section, enter the code and upload it to the ESP32.   
 
```
  #include "thingProperties.h"
  const int pingPin = 5; // Trigger Pin of Ultrasonic Sensor
  const int echoPin = 18; // Echo Pin of Ultrasonic Sensor
  #define speed 0.034

  void setup() {
    // Initialize serial and wait for port to open:
    Serial.begin(9600);
    // This delay gives the chance to wait for a Serial Monitor without blocking if none is found
    delay(1500); 

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
    // Your code here 
    float duration;
   pinMode(pingPin, OUTPUT);
   digitalWrite(pingPin, LOW);
   delayMicroseconds(2);
   digitalWrite(pingPin, HIGH);
   delayMicroseconds(10);
   digitalWrite(pingPin, LOW);
   pinMode(echoPin, INPUT);
   duration = pulseIn(echoPin, HIGH);
   cm = duration * speed / 2;


  }

```   
   
### 3 : Dashboard   
* Add a value widget to the dashboard with variable as **cm**.   
  ![exp5(1)](https://user-images.githubusercontent.com/86108610/171459755-24f37395-dda3-4098-a281-d4b236aaab31.png)   
   

### Circuit :   

![sonic3](https://user-images.githubusercontent.com/86108610/171459815-78899581-28ff-43fd-8583-ec2feb145201.png)   
 
### Working :
* Trial 1 :
  ![IMG20220601213927](https://user-images.githubusercontent.com/86108610/171459936-67d3cce4-5f57-48fe-a510-a32d3cd57039.jpg)   
  ![sonic](https://user-images.githubusercontent.com/86108610/171460026-cdb9f1bc-d347-4e88-b200-03cf70e80a1f.png)   
* Trial 2 :
  ![IMG20220601221306](https://user-images.githubusercontent.com/86108610/171460117-d130b843-f2ba-4735-a595-c13849144dfa.jpg)   
  ![sonic1](https://user-images.githubusercontent.com/86108610/171460170-fe0d66a1-2ae5-4a72-adc8-cd47548ecaae.png)   

For a detailed instruction visit :   
* [Ultra sonic distance measurement using Arduino](https://www.tutorialspoint.com/arduino/arduino_ultrasonic_sensor.htm)
* [Ultra sonic distance measurement using ESP32](https://randomnerdtutorials.com/esp32-hc-sr04-ultrasonic-arduino/)
