## Experiment 5 : Buzzer
### Description :   
_This experiment is done in order to understand the functioning of a buzzer using Arduino.A buzzer or beeper is an audio signaling device which is used as alarm devices, timers, and confirmation of user input_   
![Buzzer](https://user-images.githubusercontent.com/86108610/148684325-d885f714-7170-49ae-b36d-15c8f9fe6864.png)



### Components Used :   
* Arduino Uno
* Buzzer x 1
* Breadboard x 1
* Breadboard Jumper Wire x 2
* USB cable x 1

### Circuit :   
_Connections are made according to the Circuit given_   
![Expriment 5](https://aswin-asokan.github.io/Kerala-IoT-Challenge/files/level1/images/Circuit5.png)

### Code :

```
#define BUZZER 10
void setup() 
{
  pinMode(BUZZER, OUTPUT);
}
void loop() 
{
  digitalWrite(BUZZER, HIGH);
}
```

### Video :
_The output of this experiment would be like this :_   
<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/147457180-3af26922-6c1f-4e46-8603-72dd087804b1.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>
