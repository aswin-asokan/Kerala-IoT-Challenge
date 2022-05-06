## Experiment 2 : LED Control Using Arduino IoT Cloud

### Description :   
Arduino IoT Cloud is similar to Blynk IoT in the previous experiment but it is much easier to understand and suitable for beginners. Also unlike Blynk you can write and upload code directly from the site and there is no need to create extra templates for you smart phone.    
### Contents :
1. [Components Used](#contents-)   
2. [Steps](#steps-)   
  2.1. [Signing up and starting](#1--signing-up-and-starting)  
  2.2. [Creating variables](#2--creating-variables)   
  2.3. [Setting up device](#3--setting-up-device)   
  2.4. [Configuring Network](#4--configuring-network)   
  2.5. [Coding](#5--coding)   
  2.6. [Setting up dashboard](#6--setting-up-dashboard)   
  2.7. [Setting up mobile phone](#7--setting-up-mobile-phone)
3. [Circuit Diagram](#circuit-diagram-)
4. [Working](#working-)
### Components Used :   
* ESP 32 board
* USB cable 
* LED any colour x 1
* 220Ω resistor x 1 
* Breadboard
* Breadboard jumper wires

### Steps :
### 1 : Signing up and starting
* sign up or login to Arduino cloud
* You will get a window like this. Click __Create Thing__. You can rename it later.   
  ![Cloud1](https://user-images.githubusercontent.com/86108610/167188156-d9f6fd4f-2798-4357-ab77-e2525a05b01c.png)  
### 2 : Creating variables  
* In the next window(Setup) click on __Add Variable__ to create a variable.   
  ![Cloud2](https://user-images.githubusercontent.com/86108610/167189106-8525abd6-080e-475b-a823-4c4bedfb4fc3.png)  
* In the pop up window enter the properties of the variable.  
  ![Cloud3](https://user-images.githubusercontent.com/86108610/167189660-5c4f508f-2460-40e9-93d8-e1a6ea34e867.png)  
### 3 : Setting up device 
* Click on __Select device__ from device section in Setup window. Select __Setup a 3rd party device__.  
  ![Cloud5](https://user-images.githubusercontent.com/86108610/167190411-2e86330c-935d-49e8-8905-371172894ef9.png)  
* Select __ESP 32__.  
  ![cloud](https://user-images.githubusercontent.com/86108610/167191102-f785c832-e9b5-457c-ac78-606503ad77bb.png)   
* Choose/give a name for your device. In the next step make sure to backup secret code. 
  ![cloud7](https://user-images.githubusercontent.com/86108610/167192725-aacea023-8f19-4c83-a4b4-35013703db37.png)   
### 4 : Configuring network
* Configure network from Network Section in Setup window. 
  ![cloud9](https://user-images.githubusercontent.com/86108610/167193707-a0f59fe5-fbaa-4262-b903-f5dcd797f797.png)
### 5 : Coding
* Click on the sketch section.
* Make changes according to this code and verify it.  
  ```
  #include "thingProperties.h"
  #define LEDpin 2
  void setup() {
    // Initialize serial and wait for port to open:
    Serial.begin(9600);
    // This delay gives the chance to wait for a Serial Monitor without blocking if none is found
    delay(1500); 
    pinMode(LEDpin,OUTPUT);
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

  }

  /*
    Since LED is READ_WRITE variable, onLEDChange() is
    executed every time a new value is received from IoT Cloud.
  */
  void onLEDChange()  {
    if(lED)
    {
      digitalWrite(LEDpin,HIGH);
    }
    else
    {
      digitalWrite(LEDpin,LOW);
    }
  }
  ```  
* Before connecting and uploading the code to ESP 32 make sure you have installed Arduino Create Agent on your system.
### 6 : Setting up dashboard
* Click on __Dasboard -> Add__ from there add a Switch to your dashboard.  
  ![cloud10](https://user-images.githubusercontent.com/86108610/167195441-571efb6b-c58c-4df0-9ee2-1dc7aaa351eb.png)
* Configure it's properties and make sure to link the variable you created by clicking __Link Variable__. 
  ![cloud11](https://user-images.githubusercontent.com/86108610/167195669-d507d5f2-ed9f-4ab8-8cc0-b4486c9df6d9.png)
### 7 : Setting up mobile phone
* Install [Arduino Iot Cloud Remote](https://play.google.com/store/apps/details?id=cc.arduino.cloudiot&hl=en_IN&gl=US) on Smart phone and login to it.
* There is no need to create seperate dashboard for you phone, it will be loaded wit the one you have already created on your computer.
  ![CloudPhn](https://user-images.githubusercontent.com/86108610/167196419-6d9c4034-1cd2-4e11-9f8a-090b9a1309ef.png)
### Circuit Diagram :
![EXP2](https://user-images.githubusercontent.com/86108610/167196563-59676186-f42e-48eb-81b7-18241506fc47.png)
### Working :
<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/167199430-e658e57e-17b7-4621-8a48-895cfcbc25be.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>  
_As you can see the changes done in one device affects the other and I think the lag in switching is due to the network issues._   

For a detailed instruction visit :
* [Video 1](https://www.youtube.com/watch?v=UFCmTZUoZ1M)
* [Video 2](https://www.youtube.com/watch?v=rcCxGcRwCVk&t=568s)
