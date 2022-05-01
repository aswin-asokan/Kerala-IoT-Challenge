# Setting up the Arduino IDE for ESP-32
### Software :
_We use Arduino IDE for writing,compiling and uploading the ESP-32 codes. You can download the latest IDE from [here](https://www.arduino.cc/en/software) for linux,windows and mac._
_For more details about the IDE check [here](https://aswin-asokan.github.io/Kerala-IoT-Challenge/pages/level1/intro)_

## 1 :
After installing the Arduino IDE select __File -> Preferences__. Paste the following link in __Additional Boards Manager URLs__ field :   

```
https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json
```   
   
![SS1](https://user-images.githubusercontent.com/86108610/165939342-f3b99319-665d-4914-9393-5fdb5893711c.png)   
     
## 2 :   
Select __Tools -> Board -> Boards Manager__. Search for esp32 and install it.   
   
![SS2](https://user-images.githubusercontent.com/86108610/165940015-f4e8ce25-1608-4892-b829-f8432cad934b.png)
   
   
_For a more detailed installation process visit :_ __[Espressif](https://github.com/espressif/arduino-esp32)__
   
## 3 :   
Now try uploading a simple code and make sure the ide is working fine with ESP-32.   

__Code:__   

```
//code to blink an led
#define LED 2
void setup() {
  pinMode(LED,OUTPUT);

}

void loop() {
  digitalWrite(LED,HIGH);
  delay(500);
  digitalWrite(LED,LOW);
  delay(500);
}
```   

If the code is uploaded without any issues the LED in the board will blink with 500ms time interval.   

__Video :__   

<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/166152110-0a715cd6-ca80-4068-802a-7fd870b4e138.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>     

## Notes :  

I faced some issues while uploading the code. If you are facing similar errors try the mentioned methods. Also I'm currently using Linux mint 20.3 and I guess the methods can be tried in any ubuntu distros.   

* Error 1 :   

  ```
  "exec: "python": executable file not found in $PATH
  ```   

  * Type and run this in terminal :  
      ```
      sudo apt install python-is-python3
      ```   

* Error 2 :    

  ```
  import serial ModuleNotFoundError: No module named 'serial' exit status 1 Error compiling for board ESP32 Dev Module.
  ```    

  * Fix :   

      ```
      pip3 install pyserial
      ```   

* Error 3 :   

  ```
  Cannot open /dev/ttyUSB0: Permission denied
  ```   

  * Fix :  

      ```
      sudo usermod -a -G dialout <user_name>
      sudo chmod a+rw /dev/ttyUSB0
      ```   
   
* Sites :
   * [Error 1](https://stackoverflow.com/questions/60762378/exec-python-executable-file-not-found-in-path)
   * [Error 2](https://forum.arduino.cc/t/modulenotfounderror-no-module-named-serial/847838/2)
   * [Error 3](https://www.youtube.com/watch?v=mEptke-5rJc)
