# EX.NO-09 - Uploading Soil moisture sensor data in Thing Speak cloud

# AIM:
To upload the Soil moisture senso data in the Thing speak using an ESP32 controller.

# Apparatus required:
ESP32 Controller  </br>
HC-SR04 Ultrasonic sensor module </br>
Power supply </br>
Connecting wires </br>
Bread board </br>

# PROCEDURE:
## Arduino IDE
Step1:Open the Arduino IDE </br>
Step2: Go to sketch- include library – manage libraries file and install esp32 and thing speak library file </br>
Step3:Go to file and select new file option </br>
Step4:Type the program and update the thing speak channel ID, API key, wifi password and ID </br>
Step5:Go to file and select save option to save the program </br>
Step6:Go to sketch and select verify or compile options </br>
Step7:If no error Hex file will be generated in the temporary folder </br>
Step8: Connect all the components as per the circuit diagram </br>
Step9: Connect the programming cable with esp32 and PC.  </br>
Step10: Check the jumper position and connect 4 & 5 of P4.  </br>
Step11. Upload the program in the esp32. </br>
Step12 Press the boot button in ESP32 and then press and release the reset button after release the boot button </br>
Step13 Check the output in the cloud </br>

# THEORY:

### What is IoT?

Internet of Things (IoT) describes an emerging trend where a large number of embedded devices (things) are connected to the Internet. These connected devices communicate with people and other things and often provide sensor data to cloud storage and cloud computing resources where the data is processed and analyzed to gain important insights. Cheap cloud computing power and increased device connectivity is enabling this trend.IoT solutions are built for many vertical applications such as environmental monitoring and control, health monitoring, vehicle fleet monitoring, industrial monitoring and control, and home automation

![image](https://user-images.githubusercontent.com/71547910/235334044-c01d4261-d46f-4f62-b07f-72a7b6fce5d5.png)

### Sending Data to Cloud with ESP32 and ThingSpea
ThingSpeak is an Internet of Things (IoT) analytics platform that allows users to collect, analyze, and visualize data from sensors or devices connected to the Internet. It is a cloud-based platform that provides APIs for storing and retrieving data, as well as tools for data analysis and visualization.The Internet of Things ( or IoT) is a network of interconnected computing devices such as digital machines, automobiles with built-in sensors, or humans with unique identifiers and the ability to communicate data over a network without human intervention.Hello readers, I hope you all are doing great. In this tutorial, we will learn how to send sensor readings from ESP32 to the ThingSpeak cloud. Here we will use the ESP32’s internal sensor like hall-effect sensor and temperature sensor to observe the data and then will share that data cloud.

### What is ThingSpeak?
![image](https://user-images.githubusercontent.com/71547910/235333909-29d2e831-9fe5-4afd-b18d-f1e5d2e32518.png)
It is an open data platform for IoT (Internet of Things). ThingSpeak is a web service operated by MathWorks where we can send sensor readings/data to the cloud. We can also visualize and act on the data (calculate the data) posted by the devices to ThingSpeak. The data can be stored in either private or public channels.ThingSpeak is frequently used for internet of things prototyping and proof of concept systems that require analytics.

### Features Of ThingSpeak
ThingSpeak service enables users to share analyzed data through public channels: </br>
ThingSpeak allows professionals to prepare and analyze data for their businesses: </br>
ThingSpeak updates various ThingSpeak channels using MQTT and REST APIs: </br>
Easily configure devices to send data to ThingSpeak using popular IoT protocols. </br>
Visualize your sensor data in real-time. </br>
Aggregate data on-demand from third-party sources. </br>
Use the power of MATLAB to make sense of your IoT data. </br>
Run your IoT analytics automatically based on schedules or events. </br>
Prototype and build IoT systems without setting up servers or developing web software.</br>
Automatically act on your data and communicate using third-party services like Twilio® or Twitter®</br>

![image](https://user-images.githubusercontent.com/71547910/235334056-3ba9579f-2f62-43b1-a714-8fde6cf9ef32.png)


# PROGRAM:
```c
#define in1 6
#define in2 7
#define button 4
int rotDirection = 0;
int pressed = false;
int bs;
void setup() {
  
  pinMode(in1, OUTPUT);
  pinMode(in2, OUTPUT);
  pinMode(button, INPUT);
  digitalWrite(in1, LOW);
  digitalWrite(in2, HIGH);
}
void loop() {
   
  bs=digitalRead(button);
  if (bs==1) {
    digitalWrite(in1, HIGH);
    digitalWrite(in2, LOW);
    
    delay(20);
  }
  else if(bs==0)  {
     digitalWrite(in1, LOW);
    digitalWrite(in2, HIGH);
    delay(20);
        
  }
  
}
```

# CIRCUIT DIAGRAM:
![280510746-d1172922-a971-473d-9295-a875b81d7b26](https://github.com/Thenmozhi-Palanisamy/Soil-moisture-monitoring-using-Thing-speak/assets/95198708/2d9d6496-551d-4d1e-9858-07fd85696642)

# OUTPUT:
![280510763-e36879a7-68b6-46c2-bbeb-c491d96242c8](https://github.com/Thenmozhi-Palanisamy/Soil-moisture-monitoring-using-Thing-speak/assets/95198708/d785b01a-be2a-41a6-bf99-3739a4dad558)

# RESULT:
Thus the soil moisture sensor values are uploaded in the Thing speak using ESP32 controller.
