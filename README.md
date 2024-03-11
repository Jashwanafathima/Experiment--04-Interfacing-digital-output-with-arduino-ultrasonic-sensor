 # EXPERIMENT-NO--05-Distance measurement using Ultrasonic sensor
DATE: 08-03-2024

NAME: JASHWANA FATHIMA S

ROLL NO : 212222040059

DEPARTMENT: BE CSE


## AIM: 
To interface an ultrasonic pair and measure the distance in centimeters , calculate the error
 
### COMPONENTS REQUIRED:
1.	ultrasonic sensor module HC-SR04
2.	1 KΩ resistor 
3.	Arduino Uno 
4.	USB Interfacing cable 
5.	Connecting wires 


### THEORY: 
The HC-SR04 ultrasonic sensor uses SONAR to determine the distance of an object just like the bats do. It offers excellent non-contact range detection with high accuracy and stable readings in an easy-to-use package from 2 cm to 400 cm or 1” to 13 feet.

The operation is not affected by sunlight or black material, although acoustically, soft materials like cloth can be difficult to detect. It comes complete with ultrasonic transmitter and receiver module.
Technical Specifications
Power Supply − +5V DC
Quiescent Current − <2mA
Working Current − 15mA
Effectual Angle − <15°
Ranging Distance − 2cm – 400 cm/1″ – 13ft
Resolution − 0.3 cm
Measuring Angle − 30 degree

The ultrasonic sensor uses sonar to determine the distance to an object. Here’s what happens:

The ultrasound transmitter (trig pin) emits a high-frequency sound (40 kHz).
The sound travels through the air. If it finds an object, it bounces back to the module.
The ultrasound receiver (echo pin) receives the reflected sound (echo).
The time between the transmission and reception of the signal allows us to calculate the distance to an object. This is possible because we know the sound’s velocity in the air. Here’s the formula:

distance to an object = ((speed of sound in the air)*time)/2
speed of sound in the air at 20ºC (68ºF) = 343m/s

### FIGURE 01 CIRCUIT OF INTERFACING ULTRASONIC SENSOR 


![image](https://user-images.githubusercontent.com/36288975/166430594-5adb4ca9-5a42-4781-a7e6-7236b3766a85.png)

FIGURE 02 DISTANCE<50


![Screenshot 2024-03-08 160339](https://github.com/Jashwanafathima/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/119560192/b8b81ee0-6d76-4f80-b846-b804b4fc6f11)


FIGURE 03 DISTANCE>50


![Screenshot 2024-03-08 160403](https://github.com/Jashwanafathima/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/119560192/71ee9c5e-1acc-40be-b86e-de2c8a001756)


SCHEMATIC DIAGRAM



![Screenshot 2024-03-08 160403](https://github.com/Jashwanafathima/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/119560192/ce0afc4b-9b84-476e-a0ba-8db5581d024d)


### PROCEDURE:
1.	Connect the circuit as per the circuit diagram 
2.	Connect the board to your computer via the USB cable.
3.	If needed, install the drivers.
4.	Launch the Arduino IDE.
5.	Select the board (If you the board is arduino uno, select accordingly).
6.	Select your serial port, accordingly ( E.g. COM5 )
7.	Open the file of the program  and verify the error , clear if any errors that are existing 
8.	Upload the program and check for the physical working. 
9.	Ensure safety before powering up the device 
10.	Plot the graph for the output voltage vs the resistance 


### PROGRAM 

```
int echopin=6;
  int trigpin=7;
  int red=8;
  int green=9;long duration;
  float distance;
void setup()
{
   pinMode(echopin,INPUT);
   pinMode(trigpin,OUTPUT);
   pinMode(red,OUTPUT);
   pinMode(green,OUTPUT);
   Serial.begin(9600);
}

void loop()
{
  digitalWrite(trigpin, LOW);
  delay(10); // Wait for 1000 millisecond(s)
   digitalWrite(trigpin, HIGH);
  delay(10); // Wait for 1000 millisecond(s)
   digitalWrite(trigpin, LOW);
  duration=pulseIn(echopin,HIGH);
  distance=duration*0.034/2;
  Serial.print("distance=");
  Serial.print(distance);
  Serial.println("cms");
    if (distance>50)
  {
     digitalWrite(green, HIGH);
  delay(500);
     digitalWrite(green, LOW);
  delay(500);
  }
  else
  {
    digitalWrite(red, HIGH);
  delay(500);
     digitalWrite(red, LOW);
  delay(500);
  }
    
}
```




### Distance vs measurement table 

			
 ![robo ex4 table](https://github.com/Jashwanafathima/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/119560192/5964dcce-ab21-40af-bea5-fbfa1161470f)


 ![robo ex4 grph](https://github.com/Jashwanafathima/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/119560192/1b41aa66-763a-42d8-8183-c7e3000203f9)


			
			
			
			Average error = sum/ number of readings
   
                        Average error = 0.302
 








### RESULTS

Thus,the distance value is measured in "CM" using ultrasonic sensor

 
