## Experiment 10 : ESP32 + Firebase

### Description :   
Firebase is a platform developed by Google for creating mobile and web applications. In this experiment we use the ESP32 to connect and interact with a Firebase project, and create a realtime database to show the value from a potentiometer.
### Components Used :   
* ESP32 board
* USB cable
* Potentiometer 

### Steps :   
### 1 : Creating the Project   

After Signing into [Firebase](https://firebase.google.com/) create a new project by clicking on __Add Project__.   

![0](https://user-images.githubusercontent.com/86108610/184469247-e5501b4d-96b4-4a05-b9fe-be97f8f5aea4.png)   

![1](https://user-images.githubusercontent.com/86108610/184469294-e1eaa662-7529-48f1-8b9e-1c09b040e7f6.png)   

![2](https://user-images.githubusercontent.com/86108610/184469313-b631f274-58ab-4099-b125-a5e8e2ae13f5.png)   

![3](https://user-images.githubusercontent.com/86108610/184469326-43a25bfc-b967-4f69-9de2-26358f917f90.png)   

![4](https://user-images.githubusercontent.com/86108610/184469333-8ffeddea-e9a7-404d-931e-c6e942782454.png)   

The Project is now created.

### 2 : Creating a Realtime Database   

For creating a Realtime Database click on,   
Build -> Realtime Database -> Create Database   

![5](https://user-images.githubusercontent.com/86108610/184469399-3b8df7e6-ae77-4d0c-b8f9-0eeed22d4d33.png)   

You will be shown two options namely,
1. Start in __locked mode__
2. Start in __test mode__   
   
Select Start in __test mode__   

![6](https://user-images.githubusercontent.com/86108610/184469457-15d7bb24-0d25-405c-a485-178bf67967e2.png)   

The Database is created.

### 3 : Configuring the Database   

Click on the plus button (+) near null,   

![7](https://user-images.githubusercontent.com/86108610/184469509-c03da396-5757-4d48-87f7-261a85a1d699.png)    


Set the variable name as data and value as 0 and click Add.   

![8](https://user-images.githubusercontent.com/86108610/184469546-82d02bd4-4f6e-40d5-80db-0a907e12ff9e.png)   

Also copy the project link to use in the code.   

Before coding copy Database secret code inorder to use in our ESP32 code from,   
Project Settings -> Service Accounts -> Database Secrets   

![9](https://user-images.githubusercontent.com/86108610/184469627-acc74ae0-7418-41bb-ae66-ab5ff70e6986.png)   

After this step  the Firebase is configured, we can now move to the coding part.

### 4 : Configuring the Arduino IDE  

1. Installing libraries :
  Select, Sketch -> Include Libraries -> Manage Libraries   
  
  ![arduino1](https://user-images.githubusercontent.com/86108610/184469895-8d8ae3c3-e682-42fc-a682-0d15e254bd89.png)   
  
  Now Search for Firebase and install Firebase ESP32 Client.   
  
  ![arduino2](https://user-images.githubusercontent.com/86108610/184469989-d3eeeda5-9ed3-4d33-b499-d94795ffa513.png)

 2. Now type and upload the code to ESP32,   
 __Code :__   
 
 ```
  #include <WiFi.h>
  #include <FirebaseESP32.h>
  
  #define FIREBASE_HOST "<Project link you copied>"
  #define FIREBASE_AUTH "<Database Secret Code>"
  #define WIFI_SSID "<WiFi ID>"
  #define WIFI_PASSWORD "<WiFi Password>"


  //Define FirebaseESP32 data object
  FirebaseData firebaseData;
  FirebaseJson json;
  int pot = 35; 
  int pot_data = 0; 

  void setup()
  {

    Serial.begin(9600);

   pinMode(pot, INPUT);


    WiFi.begin(WIFI_SSID, WIFI_PASSWORD);
    Serial.print("Connecting to Wi-Fi");
    while (WiFi.status() != WL_CONNECTED)
    {
      Serial.print(".");
    }
    Serial.println();
    Serial.print("Connected with IP: ");
    Serial.println(WiFi.localIP());
    Serial.println();

    Firebase.begin(FIREBASE_HOST, FIREBASE_AUTH);
    Firebase.reconnectWiFi(true);

    //Set database read timeout to 1 minute (max 15 minutes)
    Firebase.setReadTimeout(firebaseData, 1000 * 60);
    //tiny, small, medium, large and unlimited.
    //Size and its write timeout e.g. tiny (1s), small (10s), medium (30s) and large (60s).
    Firebase.setwriteSizeLimit(firebaseData, "tiny");

    /*
    This option allows get and delete functions (PUT and DELETE HTTP requests) works for device connected behind the
    Firewall that allows only GET and POST requests.

    Firebase.enableClassicRequest(firebaseData, true);
    */

    //String path = "/data";


    Serial.println("------------------------------------");
    Serial.println("Connected...");

  }

  void loop()
  {
     pot_data = analogRead(pot);
     int Sdata = map(pot_data,0,1023,0,255);
     Serial.println(Sdata); 
     delay(100); 
     json.set("/data", Sdata);
     Firebase.updateNode(firebaseData,"/Sensor",json);
  }
 ```
    
### Circuit Diagram :   
![Potentiometer](https://user-images.githubusercontent.com/86108610/184470420-e8e19989-790b-4f99-a065-9610b7d623d3.png)   

### Result :

Adjust the Potentiometer and observe the change of value in the realtime database.   
<iframe width="352" height="240"
src="https://user-images.githubusercontent.com/86108610/184470694-7e26d878-c2ec-4ee8-ac0e-683b52968bf0.mp4"
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>  
   

_Watch this [video](https://www.youtube.com/watch?v=jpYPIh8C_sM) for a detailed explanation._
 
