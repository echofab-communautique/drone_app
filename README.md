# Falcon Drone

https://drive.google.com/open?id=0B-KGrxXLh2INUFRtWC1tYkFPS0E

----
**Components needed:** 

  * 1 	 Arduino UNO.
  * 1  	 Zippy  11.1 V  2200 mAh. 
  * 1	 Accelerometer  GY-61. 
  * 1	 Bluetooth module Hc-06 or Hc-05. 
  * 4 	 ESC 20A (Electronic Speed Control).   
  * 4 	 Brushless motor  2280kv .
  * 2 	 5in - 7in CW Propeller.
  * 2  	 5in - 7in CCW Propeller. 
  * 1  	 Protoboard. 
    -	 Wire. 
    - 	 Welding system.

----

## Knowing the components

To have a control over the project we need to know our components specifications and the features we will use. Let’s start with the Arduino UNO and the Protoboard (Figure 1) 

![arduino_1_](https://user-images.githubusercontent.com/65183668/84668658-302a8d80-af24-11ea-856b-33a3d17bc58e.png)

Figure 1: Arduino UNO over a protoboard

An Arduino is an Italian  microcontroller, which is small computer in one single Hardware and Software knowing for it’s open source environment and versatility. The Arduino UNO is the most common used by the hobbyist because of it’s low price and high quality.  

![arduino_partes](https://user-images.githubusercontent.com/65183668/84668662-30c32400-af24-11ea-96a0-6c0d37c3c0ea.png)
Figure 1.1: Arduino main parts


The arduino is composed by different electronic components such as resistances, leds, pin etc. but for this project we have to notice this seven parts (Figure 1.1). 


Red rectangle: This is the Arduino brain, the main processor of data. While developing and using our project we have to be careful with the temperature of this component; in case of a short circuit the thing you need to check first is this part. Carefully touch the component with one finger in the plastic black, if it’s hot to the touch unplugged everything wait 5 minutes and download the “Blink” Example from the arduino Software and test that is working properly. The Arduino UNO can also be in different presentation like the one shown which makes no difference just notice that the processor or the brain, is the long rectangle on the right side. (Figure 1.2) 

![arduino_otro](https://user-images.githubusercontent.com/65183668/84668660-30c32400-af24-11ea-8b27-cbafb4c5e244.png)
Figure 1.2: Arduino UNO
Aqua Rectangle: The jack for the USB connection, the component we will  to use  just for downloading the code into the Arduino.

Green Rectangle: The Reset Button. As the name suggest, the reset button is a master hardware reset, when you press it the code will star from the beginning. 

Yellow Rectangle: Digital Inputs. This is the way our Arduino receive digital data (binary)  from the sensors buttons or in this case, our motors. 

Grey Rectangle: The Tx/Rx pin is the main channel of communication for our bluetooth device. For each time you download the code you’ll need to unplug this two wires and then reconnect it after the download.  

Purple Rectangle: The Power side, this 7 pin side is about the power system our Arduino Board can share. For this project we’ll use the 5V pin 

Blue Rectangle: The  Analog Input. This is the way our Arduino receive the Analog data in this case from our accelerometer. 

Protoboard: Board  made for quick prototyping used in electronic projects such as ours.  


![gy](https://user-images.githubusercontent.com/65183668/84668690-34ef4180-af24-11ea-9e5c-e53032ccf15d.png)

Figure 2: Accelerometer GY-61


An accelerometer is a sensor made specially for measuring the propel forces, acceleration or differences in speed. Our GY-61 (Figure 2) is a 3 axis device which means that can measure the acceleration in 3 axis at the same time. Is important to distinguish each pin from each axis in order to have a correct measurement. 


![esc](https://user-images.githubusercontent.com/65183668/84668685-33be1480-af24-11ea-9b6d-f26898efeb2f.png)

Figure 3: ESC (left) and Brushless Motor (right) 


The ESC or  Electronic Speed Controller is a enclosed circuit with the purpose of vary the velocity from a electric motor such as our brushless motor. The ESC works with a PWM or a Pulse Width Modulation, that means the Arduino sends the digital signal and the device transform it into a PWM in order to activate the motor. An ESC comes with two thick wires which are connected to a battery while in the other side there are 3 thinner wires that we'll weld it with the brushless motor wires.
A brushless motor is type of motor that works with electromagnetic fields; The electricity pass through a coil which generates an electromagnetic field that interacts with magnets inside the same device resulting in a movement. (Figure 3.1)

![brushless](https://user-images.githubusercontent.com/65183668/84668666-315bba80-af24-11ea-8f55-f842d79887ef.png)
 
Figure 3.1 : Brushless Motor. Picture taken from https://img.rcgroups.com/http://www.rcuniverse.com/magazine/reviews/1344/BrushlessMotors7.jpg?h=8k6DMuRk8Hl_3aRaV0Z_Dg) 


![blue](https://user-images.githubusercontent.com/65183668/84668664-315bba80-af24-11ea-94d1-4a75dc781a73.png)

Figure 4: Bluetooth module


A Bluetooth module (Figure 4) is an enclosed circuit made for wireless communication using radio frequency based on serial communication. We have to be very careful with the connections of the Bluetooth; The device has two pin named TX and RX that means one is the Receiver and the other is the Transmitter, saying that we have to connect the RX from the module into the TX of the Arduino, in that way we have one Receiver connected to one Transmitter, same happen  with the TX of the Bluetooth, but we will explain in a more detail way  in the connections chapter 


## Connections

Let’s begin the project with the electronic connections. We already saw what are the main parts of the Arduino so from now until the end should be easy to identify where to connect the components. 
First we will connect one wire or jumper for in order to give power to our Protoboard. We need to connect the 5V in the + of the Protoboard, the - will be connected in the GND or Ground  (Figure 5) 

![connection](https://user-images.githubusercontent.com/65183668/84668682-33257e00-af24-11ea-8767-4a1eb27a20c1.png)
Figure 5: Giving power to the Protoboard


Once we have our two wires connected is moment to connect our first component the Accelerometer. We have to remember that the order of connections in this device are really important, because you need to connect exactly the same as shown if you don’t do so, your lectures will be in a different axis. 

![acc](https://user-images.githubusercontent.com/65183668/84668657-302a8d80-af24-11ea-82c3-bb52b751dc7b.png)

Figure 6: Accelerometer connections)


Having this view from the accelerometer in our protoboard, this are the following connections:
White wire:  (-) Negative, GND or Ground.
Blue wire:  Goes to the A0 from the Analog Inputs in the Arduino.
Yellow wire: Goes to the A1 from the Analog Input in the Arduino. 
Green wire: Goes to the A3 from the Analog Input in the Arduino.
Orange wire: (+) Positive, 5V or VCC. 
So at the end of the connections the Arduino should look like the Figure 6.1.

![conexion_acelerometro](https://user-images.githubusercontent.com/65183668/84668670-31f45100-af24-11ea-82a0-71f4806e8e1d.png)
Figure 6.1: Connections from the Arduino perspective


Once our Accelerometer is connected, We have to connect the  Bluetooth device. Remember that in the back of our module all the connections are labeled (Figure 4). That means the VCC is the 5V or (+) of our power source and GND is the negative (-). Keeping that in mind should be easy to made the connections. It is really important that the RX from the Bluetooth module is connected to the TX in the arduino, the TX makes reference to “Transmitter” if you connect the two TX you will have two transmitters crashing and two receivers that are not receiving anything. After all the connections the module should look like the Figure 7. 

![bluecone](https://user-images.githubusercontent.com/65183668/84668665-315bba80-af24-11ea-844b-4432b67f2997.png)
(Figure 7: Bluetooth connections) 
With this perspective the module is connected to the arduino in this way.
Grey wire:  Tx in the Arduino.
Yellow wire: RX in the Arduino.
Red wire: VCC, 5V, (+) 
Black wire: GND (-) 
The connections should look like the one in Figure 7.1  in the Arduino. 


![conexion_arduino_7 1](https://user-images.githubusercontent.com/65183668/84668678-328ce780-af24-11ea-9f9b-58e4dbe1b5ba.png)
Figure 7.1 Connections from the Bluetooth module






The last connection is divided in three phases. The first phase weld the ESC to the Brushless motor. The important aspect from this welding is the fact that we have to make two motors spin at different direction from the others two (FIgure 8). The reason is very simply, if all the motors are spinning at the same direction the moment or torque generated from all the propellers will cause the drone to spin out of control in the same direction of the motor. Changing the direction of two of them will cause an equilibrium  and the Quadcopter will stay still.   


![motoresdrone](https://user-images.githubusercontent.com/65183668/84668692-3587d800-af24-11ea-9e71-2324d6b60892.png)
Figure 8: Rotation of the motors picture taken from
http://noticiasdelaciencia.com/upload/img/periodico/img_25686.jpg


Two of the connections between the ESC and the motor is shown in the figure 8.1 where the cable A from the ESC is connected to the center of the motor, the cable B is connected to the left cable of motor and the cable C is connected to the right cable in the motor. Remember to protect the welding when finished with thermofit or tape. 

![escconmotor](https://user-images.githubusercontent.com/65183668/84668686-33be1480-af24-11ea-96b6-8816791e34ba.png)
Figure 8.1 : Brushless motor and ESC welding



The other two are connected differently, The wire A is a common GND so we’ll have to change the B for the C as shown in the pictures below 


![motorescambio](https://user-images.githubusercontent.com/65183668/84668691-34ef4180-af24-11ea-9c11-05e048221335.png)
Figure 8.2: The connection in the ESC, notice the colors of the cable.  
Figure 8.3: The connection in the motor for one direction 
Figure 8.4: The connection has been changed to change the direction, notice the white wire has been changed for the red wire keeping the same configuration that was shown in the figure 8.2 



At the end of the connections  is recommended to weld them in order to avoid failures. If you decide to do it, you will have 4 Motors with its respective ESC, two switched and two direct ones as the Figure 8.4
![todosmotores](https://user-images.githubusercontent.com/65183668/84668697-36206e80-af24-11ea-9989-f8e64ca0fd59.png)
Figure 8.4: All the motors connected



The second stage is the welding of the power system or the thick wires. We  have to connect all the red cables of the ESCs to each other, after that do the same thing with the black wires. Not between black and red (Figure 8.5, 8.6 and 8.7) If the cable from the battery or the ESC is not long enough you can weld another wire keeping in mind that has to be the same thickness or caliber, otherwise the current will break it. 

![welding](https://user-images.githubusercontent.com/65183668/84668699-36206e80-af24-11ea-94c2-eaeb809c716d.png)
Figure 8.5: Welding the wires 

![diagrama](https://user-images.githubusercontent.com/65183668/84668684-33be1480-af24-11ea-9b67-9da7ef44469b.png)
Figure 8.6: diagram of connection)

![conecciones](https://user-images.githubusercontent.com/65183668/84668667-31f45100-af24-11ea-9018-317f0d3d9279.png)
Figure 8.7:All the wires welded and covered by tape



Our last connection is between  the ESC and the Arduino. The other 3 little wires from the other side is the communication between the Arduino and the ESC. The color of the wires can be different from each ESC but normally they keep either the black for GND the red for VCC and the different color for the communication or Yellow for communication, red from VCC and a darker color for GND. (Figure 8.8 ) 


![wires](https://user-images.githubusercontent.com/65183668/84668654-2f91f700-af24-11ea-9535-7538c3fd545c.png)

Figure 8.8: Brown wire is GND, red wire is VCC and yellow wire is signal 


Following this the connections should not be a problem just keep the continuity and connect the VCC and GND. The signal should be connected into the digital side of the Arduino, the pins 9 through 12 are the ones where the ESC can be connected.  (Figure 8.9)

![pins](https://user-images.githubusercontent.com/65183668/84668695-36206e80-af24-11ea-930e-4c7f49869848.png)
Figure 8.9: Pins reserved for the ESCs


Our connections are done by now. To summarize:
Bluetooth: Vcc, TX into the RX of the arduino and Rx into the TX of the arduino and GND
Accelerometer: 3 wires in the arduino, Vcc and GND
ESC: All the red  and black ones connected in parallel 3 wires to the motor and 3 extra wires ; one for the Vcc of the Arduino, one for the GND of the arduino and one for the signal. 



## Code of the Arduino.


Once our hardware is connected we develop our software. Before we download our final code we have to calibrate our motors and ESC. The reason to calibrate is because our motors respond with a three phase signal (Figure 9.1) changing the order of the wires change the order of the phases which results in a change of the rotation.  

![phases](https://user-images.githubusercontent.com/65183668/84668693-3587d800-af24-11ea-8edf-c7cbfd8ebf5a.png)
(Figure 9.1)


Calibration:
To calibrate we use this code, Note that after each “//” is a comment not part of the logic. 

``` 
#include <Servo.h>//Includes the library Servo which we need for the motors. 
Servo mot;  //Declare the objects Servo
Servo mot2;
Servo mot3;
Servo mot4;




const int pinServo = 9; // Output pin
const int pinServo2 = 10;
const int pinServo3 = 11;
const int pinServo4 = 12;




int angulo;          //Value to control the velocity 
int pulsoMin = 1000; //This two values controls the maximum and minimum of pulse.
int pulsoMax = 2000;




void setup() {
  mot.attach(pinServo, pulsoMin, pulsoMax); //Configures  the characteristics of each motor with the pulses of the ESC 
  mot2.attach(pinServo2, pulsoMin, pulsoMax);
  mot3.attach(pinServo3, pulsoMin, pulsoMax);
  mot4.attach(pinServo4, pulsoMin, pulsoMax);
  
  
}


void loop(){
 
 
    
  angulo=180;          //Gives the pulse to start 
  mot.write(angulo);    
  mot2.write(angulo);  
  mot3.write(angulo);  
  mot4.write(angulo);
  delay(4000);


   angulo=0; 
         // The value can be between 0 and 180 
    mot.write(angulo);    
    mot2.write(angulo);  
    mot3.write(angulo);  
    mot4.write(angulo);
    delay(3000);
   
  }
  ```

We have to notice that the behaviour of the motors will be 3 seconds in maximum velocity and 4 seconds off. That is to have the same sequence and phase in all the motors. 


### Code for flying. 

```
#include <Servo.h> //Library Servo for the motors
Servo mot;         //Declare the motors as servos
Servo mot2;
Servo mot3;
Servo mot4;


const int pinServo = 9;  //Pin for the servos 
const int pinServo2 = 10;
const int pinServo3 = 11;
const int pinServo4 = 12;




int angulo;              //Variable for the velocity
int pulsoMin = 1000;     //Maximum and minimum pulse
int pulsoMax = 2000;
int estado = 'a';        //Send the motors to the state a or still


//Pin for the analog input 
const int xPin = 0;
const int yPin = 1;
const int zPin = 2;




//The minimum and maximum from the accelerometer 
int minVal = 333;
int maxVal = 405;
int a;
int angulo2;     //Values for each motor 
int angulo3;
int angulo4;
int angulo5;




//Variables to save the velocity 
double x;
double y;
double z;
double xmax; //Variables to save the calibration data 
double xmin;
double ymax;
double ymin;
double zmax;
double zmin;




void setup() {
  mot.attach(pinServo, pulsoMin, pulsoMax);  //Fix the characteristics for each motor 
  mot2.attach(pinServo2, pulsoMin, pulsoMax);
  mot3.attach(pinServo3, pulsoMin, pulsoMax);
  mot4.attach(pinServo4, pulsoMin, pulsoMax);
  Serial.begin(9600);
}


void loop() {
 




  //Read the values from the accelerometer
  int xRead = analogRead(xPin);
  int yRead = analogRead(yPin);
  int zRead = analogRead(zPin);


  //Convert the data into degrees 
  int xAng = map(xRead, minVal, maxVal, -90, 90);
  int yAng = map(yRead, minVal, maxVal, -90, 90);
  int zAng = map(zRead, minVal, maxVal, -90, 90);


  //Convert the data from Rad to Deg
  x = RAD_TO_DEG * (atan2(-yAng, -zAng) + PI);
  y = RAD_TO_DEG * (atan2(-xAng, -zAng) + PI);
  z = RAD_TO_DEG * (atan2(-yAng, -xAng) + PI);






   
   if (a==0){    //Creates a state to initate  
     
     xmax = x; 
     xmin = x;
     ymax = y;
     ymin = y;
     zmax = z;
     zmin = z;
     a = 2;
     
   }
  


 
   
   if (x==xmax && y==ymax && z==zmax){  //Detect if the drone is stable 
  mot.write(angulo);
  mot2.write(angulo);
  mot3.write(angulo);
  mot4.write(angulo);
   }
     
   if (y<ymin &&  z>zmax ){            //Detect and stabilize
     angulo2=angulo;
     angulo2+4;
     mot4.write(angulo2);
   }
    if (x<xmax && y<ymin && z<zmin){  //Detect and stabilize
     angulo3=angulo;
      angulo3+4;
     mot3.write(angulo3);
   }
    if (x>xmin && y>ymax && z>zmax){ //Detect and stabilize
      angulo4=angulo;
     angulo4+4;
     mot2.write(angulo4);
   }
     if ( y>ymax && z<zmin){         //Detect and stabilize
       angulo5=angulo;
    angulo5+4;
     mot.write(angulo5);
   }
  delay(100);
     
  if(Serial.available()>0){
    estado = Serial.read();
  //Read the signal from the App 
  
  }
  
  if (estado=='b'){            //Stop the motors
    
  angulo=0;
  mot.write(angulo);    
  mot2.write(angulo);  
  mot3.write(angulo);  
  mot4.write(angulo);
  
  }
  if (estado=='a'){           //increase the velocity in the motors  
    ++angulo;
    mot.write(angulo);    
    mot2.write(angulo);  
    mot3.write(angulo);  
    mot4.write(angulo);
  }
  if (estado=='c'){          //Slow down the motors
    --angulo;
    mot.write(angulo);    
    mot2.write(angulo);  
    mot3.write(angulo);  
    mot4.write(angulo);
    
  }
  if (estado=='d'){          //Slow down the motors to turn 
    angulo4=angulo;
    angulo3=angulo;
    angulo4+6;
    angulo3+6;  
    mot2.write(angulo4);  
    mot3.write(angulo3);  
    delay(1000);
    
  }
   if (estado=='e'){          //Slow down the motors to turn
    angulo2=angulo;
    angulo5=angulo;
    angulo2+6;
    angulo5+6;  
    mot.write(angulo5);  
    mot4.write(angulo2);  
    delay(1000);
    
  }
    if (estado=='f'){          //Slow down the motors to turn
    angulo3=angulo;
    angulo2=angulo;
    angulo3+6;
    angulo2+6;  
    mot3.write(angulo3);  
    mot4.write(angulo2);  
    delay(1000);
    
  }
     if (estado=='h'){          //Slow down the motors to turn
    angulo5=angulo;
    angulo4=angulo;
    angulo5+6;
    angulo4+6;  
    mot.write(angulo5);  
    mot2.write(angulo4);  
    delay(1000);
    
  }
     if (estado=='i'){          //Slow down the motors to turn
    angulo5=angulo;
    angulo3=angulo;
    angulo5+6;
    angulo3+6;  
    mot.write(angulo5);  
    mot3.write(angulo3);  
    delay(1000);
    
  }
     if (estado=='j'){          //Slow down the motors to turn
    angulo4=angulo;
    angulo2=angulo;
    angulo5+6;
    angulo3+6;  
    mot2.write(angulo4);  
    mot4.write(angulo2);  
    delay(1000);
    
  }
  
  estado='z';              //Variable for debug  
 
}
 ```
