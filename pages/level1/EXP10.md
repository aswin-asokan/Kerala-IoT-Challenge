## Experiment 10 : IR Remote Control Using TSOP
### Description :   
_An IR receiver can detect bursts of infrared light sent by a common remote controller (like for a television), and then output a pattern of high/low signals to a Propeller I/O pin. In this experiment we use a IR receiver to identify and respond to a remote_
### Pin Diagram :   
![diagram](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/ir.png)   
### Experiment 10.1 : Decoding IR remote codes
_First we need to decode the IR remote codes. For this the given circuit is created and required remote codes are acquired from the serial monitor_   
#### Components Used
* Arduino Uno Board
* Infrared Remote Controller(TV Remote or any other remote) 
* Infrared Receiver x 1
* Breadboard Wire x 3
* USB cable
#### Circuit :
![circuit](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/Circuit10a.png)   
#### Code :

```
#include<IRremote.h>
const int RECV_PIN = 12;
IRrecv irrecv(RECV_PIN);
decode_results results;
void setup() 
{
  Serial.begin(9600);
  irrecv.enableIRIn();
}
void loop() 
{
  if(irrecv.decode(&results))
  {
    Serial.println(results.value,HEX);
    irrecv.resume();
  }
}
```
   
#### Serial Monitor Output :
![circuit](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/serial.png)   
_Now we have have the corresponding codes for required remote buttons and also ignore the FFFFFFFF. I've used numbers 1 to 6 in the remote_   

### Experiment 10.2 : IR Remote Control   
_As we got the codes now it's time to use it in the actual code to make LED switch on and off according to the button pressed._   
### Components Used :
* Arduino Uno Board
* Infrared Remote Controller(TV Remote or any other remote) 
* Infrared Receiver 1
* LED Green x 2
* LED Yellow x 2
* LED Red x 2
* 220Ω Resistor x 6
* Breadboard Wire x 10
* USB cable

### Circuit :
![Circuit10](https://user-images.githubusercontent.com/86108610/147741039-9560fbb9-42db-4cf3-b7a4-507b1206c2ce.png)

### Code :

```
#include<IRremote.h>
const int RECV_PIN = 12;
int LED[6]={7,6,5,4,3,2};
int togglestate[6]={0,0,0,0,0,0};
long remote[6]={0x1FE50AF,0x1FED827,0x1FEF807,0x1FE30CF,0x1FEB04F,0x1FE708F};//change the values with codes yo got from your remote
int i;
IRrecv irrecv(RECV_PIN);
decode_results results;
void setup()
{
  irrecv.enableIRIn();
  for(i=0;i<6;i++)
  {
    pinMode(LED[i],OUTPUT);
  }
}
void loop()
{
  if(irrecv.decode(&results))
  {
    for(i=0;i<6;i++)
    {
      if(results.value==remote[i])
      {
        if(togglestate[i]==0)
        {
          digitalWrite(LED[i],HIGH);
          togglestate[i]=1;
        }
        else
        {
          digitalWrite(LED[i],LOW);
          togglestate[i]=0;
        }
      }
      irrecv.resume();
    }
  }
}
```   
_Refer to this [**Video**](https://www.youtube.com/watch?v=8E3ltjnbV0c) to learn about remote codes. Also, refer the [**Video**](https://www.youtube.com/watch?v=FRhzuWl39qg) by [**Sci-COPATH**](https://www.youtube.com/channel/UCeATKlkbBC8xT7r8hmK26EQ) to understand array._    
### Video :
<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/147742163-87ecdb39-4c5b-4aa9-bdd4-cc77e1cd27f6.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>
   
### Picture :
![EXP10](https://user-images.githubusercontent.com/86108610/147740626-b9ac88f1-97b8-4812-8ed2-44471691a6c3.png)
