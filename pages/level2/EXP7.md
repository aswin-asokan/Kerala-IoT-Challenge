## Experiment 7 : MIT App Inventor + ESP 32

### Description :  
MIT App Inventor is a web application integrated development environment for creating Mobile Apps originally provided by Google, and now maintained by the Massachusetts Institute of Technology. In this experiment we are going to build a android app (apk) which communicates with Node MCU .
    
### Components Used :   
* ESP32 board
* USB cable 
* LED Red x 1
* LED Yellow x 1
* LED Green x 1
* 220Ω resistor x 3 
* Breadboard
* Breadboard jumper wires   

### Steps :   
### 1 : Dowload Source Code   
Dowload source code for both MIT app inventor and ESP32 as ZIP from this [Link](https://github.com/mo-thunderz/Esp32BluetoothApp).    

![1](https://user-images.githubusercontent.com/86108610/172552512-468b0ce7-4933-40ff-8798-cd23451e862f.png)

### 2 : Upload code to ESP32
After extracting the file you can see the code for ESP32 in a folder named Arduino. Open and upload it to the ESP32. You can also change the code as you wish.   

```
#include "BluetoothSerial.h" 

// init Class:
BluetoothSerial ESP_BT; 

// init PINs: assign any pin on ESP32
int led_pin_1 = 15;
int led_pin_2 = 2;
int led_pin_3 = 4;     

// Parameters for Bluetooth interface
int incoming;

void setup() {
  Serial.begin(19200);
  ESP_BT.begin("ESP32_Control"); //Name of your Bluetooth interface -> will show up on your phone

  pinMode (led_pin_1, OUTPUT);
  pinMode (led_pin_2, OUTPUT);
  pinMode (led_pin_3, OUTPUT);
}

void loop() {
  
  // -------------------- Receive Bluetooth signal ----------------------
  if (ESP_BT.available()) 
  {
    incoming = ESP_BT.read(); //Read what we receive 

    // separate button ID from button value -> button ID is 10, 20, 30, etc, value is 1 or 0
    int button = floor(incoming / 10);
    int value = incoming % 10;
    
    switch (button) {
      case 1:  
        Serial.print("Button 1:"); Serial.println(value);
        digitalWrite(led_pin_1, value);
        break;
      case 2:  
        Serial.print("Button 2:"); Serial.println(value);
        digitalWrite(led_pin_2, value);
        break;
      case 3:  
        Serial.print("Button 3:"); Serial.println(value);
        digitalWrite(led_pin_3, value);
        break;
    }
  }
}
```   

### 3 : Create app   
Start a new project in [MIT App Inventor](https://appinventor.mit.edu/) and import the project from extracted folder.   
![2](https://user-images.githubusercontent.com/86108610/172553567-2684ce3c-dbd9-436e-b908-2ea78f168237.png)

### 4 : Using the app   
You can either build an apk for the app and install it in your phone or connect it via [MIT A12 Companion](https://play.google.com/store/apps/details?id=edu.mit.appinventor.aicompanion3&hl=en_IN&gl=US).

![3](https://user-images.githubusercontent.com/86108610/172554076-1ceec1b7-3529-4a09-9f0a-0ef46095037d.png)

![4](https://user-images.githubusercontent.com/86108610/172554097-5a763e0b-2864-4154-a15b-92b640976bd0.png)

You will get a pop up with a QR code in both the options scan it with companion app to use it or to download it.

### 5 : Using the app   
Pair your ESP32 with your phone via Bluetooth and connect it through the MIT app to control the board.   

### Circuit Diagram :   

![5](https://user-images.githubusercontent.com/86108610/172555723-807dd60f-3f88-4a2a-8f94-17dd0df4a388.png)

### Working :   

<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/172566850-45d246b0-d4d1-44e5-be86-0baf96bac12a.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>  

_Watch this [video](https://www.youtube.com/watch?v=aM2ktMKAunw) for a detailed explanation._
