## Experiment 8 : MIT App Inventor - Bidirectional Communication

### Description :   
In this experiment we will transmit data between MIT app and ESP32 ( bi-directional ). We will send data to ESP32, to switch on the LED and after the timer it automatically turns off. When this happens ESP32 sends a byte to turn off the button in the app.

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
### 1 : Creating the app   
Edit the app made in the [previous experiment](https://aswin-asokan.github.io/Kerala-IoT-Challenge/pages/level2/EXP7) like the blocks given below. First add a clock block and the remaining blocks inside it.    

![exp8(1)](https://user-images.githubusercontent.com/86108610/172750136-2c811627-ba01-4b3f-8b68-727bc173a851.png)   

### 2 : Upload code to ESP32   

```
#include "BluetoothSerial.h" 

// definition of the delaytime between button on and button off
#define DELAY 1000                      // delay is in milliseconds, so 1000ms corresponds to 1s

// init Class:
BluetoothSerial ESP_BT; 

// init PINs: assign any pin on ESP32
int led_pin_1 = 15;
int led_pin_2 = 2;
int led_pin_3 = 4;                      

// Parameters for Bluetooth interface and timing
int incoming;                           // variable to store byte received from phone 
unsigned long now;                      // variable to store current "time" using millis() function
unsigned long time_button1;             // timestamp for button1 to 3 -> stores time when button is enabled
unsigned long time_button2;
unsigned long time_button3;

void setup() {
  Serial.begin(19200);
  ESP_BT.begin("ESP32_Control");        // Name of your Bluetooth interface -> will show up on your phone

  pinMode (led_pin_1, OUTPUT);          // Define output ports to connect LEDs
  pinMode (led_pin_2, OUTPUT);
  pinMode (led_pin_3, OUTPUT);
}

void loop() {
  now = millis();                       // Store current time

  // time-out check -> check if a button is on and whether it needs to be switched off
  if(digitalRead(led_pin_1) and now > time_button1 + DELAY) {     // if output port (led_pin_1) is active and if the delay time has passed, the button is to be switched off
    digitalWrite(led_pin_1, 0);                                   // set output port to 0
    ESP_BT.write(10);                                             // send byte to phone indicateding that Button 1 is to be set to 0 -> 10
    Serial.print("Button 1 timeout - value: 0");                  // write to serial port for easy debugging
  }
  if(digitalRead(led_pin_2) and now > time_button2 + DELAY) {
    digitalWrite(led_pin_2, 0);
    ESP_BT.write(20);                                             // send byte to phone indicateding that Button 2 is to be set to 0 -> 20
    Serial.print("Button 2 timeout - value: 0");
  }
  if(digitalRead(led_pin_3) and now > time_button3 + DELAY) {
    digitalWrite(led_pin_3, 0);
    ESP_BT.write(30);                                             // send byte to phone indicateding that Button 3 is to be set to 0 -> 30
    Serial.print("Button 3 timeout - value: 0");
  }
  
  // -------------------- Receive Bluetooth signal ----------------------
  if (ESP_BT.available()) 
  {
    incoming = ESP_BT.read(); //Read what we receive and store in "incoming"

    // separate button ID from button value -> button ID is 10, 20, 30, etc, value is 1 or 0
    int button = floor(incoming / 10);
    int value = incoming % 10;
    
    switch (button) {
      case 1:  
        Serial.print("Button 1:"); Serial.println(value);
        digitalWrite(led_pin_1, value);
        if(value == 1)                                            // check if the button is switched on
          time_button1 = now;                                     // if button is switched on, write the current time to the timestamp
        break;
      case 2:  
        Serial.print("Button 2:"); Serial.println(value);
        digitalWrite(led_pin_2, value);
        if(value == 1)
          time_button2 = now;
        break;
        case 3:  
        Serial.print("Button 3:"); Serial.println(value);
        digitalWrite(led_pin_3, value);
        if(value == 1)
          time_button3 = now;
        break;
    }
  }
}
```

### 3 : Connecting to the app   
Like the previous experiment pair with the ESP32 via bluetooth and try out the experiment.   

### Circuit Diagram :   

![5](https://user-images.githubusercontent.com/86108610/172555723-807dd60f-3f88-4a2a-8f94-17dd0df4a388.png)

### Working :   

<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/172755743-74ab0cf4-5114-4453-9d92-0185e56fe063.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>  

_Watch this [video](https://www.youtube.com/watch?v=OvWd_xZ12E4) for a detailed explanation._
