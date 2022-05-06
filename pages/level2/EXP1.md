## Experiment 1 : Hello World LED Program Using Blynk App   
### Description :   
Blynk is a new platform that allows you to quickly build interfaces for controlling and monitoring your hardware projects from your iOS and Android device.Here we are using the Blynk app to control a LED connected to ESP-32 from our system and phone.   
__Follow this [link](https://blynk.io/) and join Blynk and start off the experiment.__   

### Components Used :      
* ESP 32 board
* LED x 1 Nos
* Breadboard
* Micro USB Cable
* Breadboard jumper wires   

### Step 1 :   
After joining to blynk cloud you have to create a template for that follow the instructions.   
#### 1 :   
![blynk1](https://user-images.githubusercontent.com/86108610/166209519-c4d53171-54c5-4a79-bd42-4dff8f9815af.png)
#### 2 :   
**Choose a name and create the template.**    
![blynk2](https://user-images.githubusercontent.com/86108610/166209537-f63d9a79-fd03-46ce-aeb8-da0b711f5e2e.png)
### 3 :   
* **Select datastream.**   
![blynk3](https://user-images.githubusercontent.com/86108610/166209562-0f002721-3a8a-4abd-ade1-cb8d3070ebb9.png)
* **Enter the details of datastream.**   
![blynk4](https://user-images.githubusercontent.com/86108610/166209574-cd155a25-5190-4225-a7c4-040d919e473d.png)
### 4 :   
* **Now select web dashboard and add a switch to your dashboard.**   
![blynk5](https://user-images.githubusercontent.com/86108610/166209588-54a4ef7b-bf6e-4860-a85b-0e24088d93e1.png)
* **Select the settings of the switch and datastream to the one we have created.**    
![blynk6](https://user-images.githubusercontent.com/86108610/166209695-d9a02194-11a9-429a-95c1-199024b78375.png)   

### Step 2 :   
* Now to the coding part. For that first downlod blynk library [Zip](https://github.com/blynkkk/blynk-library) and include it to the IDE by selecting **Sketch -> Include library -> Add .ZIP library.**
![menu](https://user-images.githubusercontent.com/86108610/166210702-6fa02221-2c7e-4e47-b32a-4cce123645bd.png)   

* Now add code from File -> Example.   
![menu2](https://user-images.githubusercontent.com/86108610/166211097-77173cce-b2de-4780-9c97-0e6fbcd982bb.png)   

* In the code replace
  ```
  //#define BLYNK_TEMPLATE_ID           "TMPLxxxxxx"
  //#define BLYNK_DEVICE_NAME           "Device"
  ```
  With the template ID and device name given in blynk.
  ![blynk7](https://user-images.githubusercontent.com/86108610/166211758-bdf6e90b-74b6-437d-98ad-ca86f3dcc0c3.png)   
  After enter the remaining code for blinking the LED :   
  ```
  // Fill-in information from your Blynk Template here
  #define BLYNK_TEMPLATE_ID "TMPLpc4K270H"
  #define BLYNK_DEVICE_NAME "LED Blink"

  #define BLYNK_FIRMWARE_VERSION        "0.1.0"

  #define BLYNK_PRINT Serial
  //#define BLYNK_DEBUG
  #define APP_DEBUG

  // Uncomment your board, or configure a custom board in Settings.h
  //#define USE_WROVER_BOARD
  //#define USE_TTGO_T7

  #include "BlynkEdgent.h"
  BLYNK_WRITE(V0)
  {
    int pinValue = param.asInt();
    digitalWrite(15,pinValue);
  }
  void setup()
  {
    pinMode(15,OUTPUT);
    Serial.begin(115200);
    delay(100);

    BlynkEdgent.begin();
  }
  void loop() {
    BlynkEdgent.run();
  }
  ```   
  
### Step 3 :
Now we are left off with configuring dashboard from our mobile. For that install [Blynk IoT](https://play.google.com/store/apps/details?id=cloud.blynk&hl=en_IN&gl=US) app from playstore (as I'm using an android device).    
After installing the app login with the same profile created in the website.   
#### 1 :
* Click on **Add New Device** option in the.
![blynk1](https://user-images.githubusercontent.com/86108610/166213391-26545333-bc8c-45d3-903a-32cb56445444.png)   

* Select **Connect to Wifi**.   
![blynk2](https://user-images.githubusercontent.com/86108610/166213510-063e5155-d91a-4e26-807f-9625df6adc8b.png)   

* Connect to your ESP32 board.   
* Now setup the dashboard in your mobile.   
![blynk3](https://user-images.githubusercontent.com/86108610/166214410-8d014a1d-b072-4318-8adb-4c012fdfeb90.png)   

* Add a switch widget to your dashboard.    
![blynk4](https://user-images.githubusercontent.com/86108610/166214485-25e7c8e8-f31d-4371-bac8-5f7fefa1192d.png)   

* In it's settings select datastream to the one we created and configure it as you like.   
![blynk5](https://user-images.githubusercontent.com/86108610/166214572-c7fcb64b-f170-47f8-9d14-b2c971ad8ecf.png)   

* Now you can control the LED from you mobile or PC.
  * Mobile :   
  ![blynk6](https://user-images.githubusercontent.com/86108610/166214677-74b861c4-8f74-4e1a-8d34-5cf0f3886615.png)   

  * PC :   
  ![blynk7 (1)](https://user-images.githubusercontent.com/86108610/166214929-8a8673b9-8351-4c07-a860-473377774f19.png)

### Circuit Diagram :   
![EXP1](https://user-images.githubusercontent.com/86108610/166215807-3952edeb-699e-468e-95e7-5cda239d7116.png)

### Working :   
<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/166216112-77bb8d51-90d5-44a8-9c9b-54ad4d845647.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>  

_For a detailed instruction you can see this [video](https://www.youtube.com/watch?v=IKbbvEzZ7wg)_
