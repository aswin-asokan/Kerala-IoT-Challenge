## Experiment 8 : MIT App Inventor - Creating a Reliable Communication

### Description :   
In the previous two experiments the length of the communication was limited to a single byte. In this experiment we will send over values larger than 256.

### Components Used :   
* ESP32 board
* USB cable 

### Steps :   
### 1 : Creating the app   
Edit the app or import this project :   
[File.zip](https://github.com/aswin-asokan/Kerala-IoT-Challenge/files/8892022/File.zip)
### 2 : Upload code to ESP32   

```
#include "BluetoothSerial.h" 
BluetoothSerial ESP_BT; 
int incoming;                 
int id = -1;                           
int val_byte1 = -1;                    
int val_byte2 = -1;                     

void setup() 
{
  Serial.begin(19200);
  ESP_BT.begin("ESP32_Control");        

}

void loop() 
{
  if (ESP_BT.available()) 
  {
    incoming = ESP_BT.read();   

    if (incoming > 127) 
    {              
      reset_rx_BT();                   
      id = incoming - 128;             
    }
    else if (val_byte1 == -1)
    {   
      val_byte1 = incoming;             
    }
    else if (val_byte2 == -1) 
    {   
      val_byte2 = incoming;  
      int value = 128*val_byte1 + val_byte2;  
      Serial.print("Id: "); Serial.print(id); Serial.print(", val: "); Serial.println(value);   
      send_BT(id, value);            
      reset_rx_BT();                
    }
  }
}

void reset_rx_BT() 
{                    
  id = -1;
  val_byte1 = -1;
  val_byte2 = -1;
}
void send_BT(int id, int value) 
{   
  ESP_BT.write(128 + id);
  ESP_BT.write(floor(value/128));       
  ESP_BT.write(value%128);              
}
```

### 3 : Connecting to the app   
Like the previous experiment pair with the ESP32 via bluetooth and try out the experiment.   

### Working :   

<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/173382671-eb0d13fa-7a99-468f-8a67-e9384037f5fd.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>  

_Watch this [video](https://www.youtube.com/watch?v=eP35zgZnQY4&t=1987s) for a detailed explanation._
