# Interfacing-And-Controlling-Digital-Output-With-Development-Board-And-Ultrasonic-Sensor

# NAME: MURUGA.S

# REG NO: 212225040265

# AIM:
To interface an HC-SR04 ultrasonic sensor with an Arduino Uno and control a digital output (LED) based on the measured distance of an object.

# COMPONENTS REQUIRED:

1.Ultrasonic Sensor

2.1 KΩ resistor

3.Arduino Uno

4.USB Interfacing cable

5.Connecting wires

# Algorithm:

1.Initialize the TRIG, ECHO, and LED pins of the Arduino.
2.Generate a 10-microsecond trigger pulse using the ultrasonic sensor.
3.Read the echo pulse duration using the pulseIn() function.
4.Calculate the distance in centimeters using the echo duration.
5.If the distance is below the predefined threshold, turn ON the LED; otherwise, turn OFF the LED.
6.Display the measured distance in the Serial Monitor and repeat the process continuously.

# Procedure:

1.Open Tinkercad Circuits and create a new circuit.
2.Place an Arduino Uno, HC-SR04 ultrasonic sensor, LED, and suitable resistor in the workspace.
3.Connect the VCC pin of the ultrasonic sensor to the Arduino 5V pin.
4.Connect the GND pin of the ultrasonic sensor to the Arduino GND.
5.Connect the TRIG pin of the ultrasonic sensor to a digital pin of the Arduino.
6.Connect the ECHO pin of the ultrasonic sensor to another digital pin of the Arduino.
7.Connect the LED to a digital output pin through a suitable resistor.
8.Write the Arduino program to generate a trigger pulse and calculate the distance using the echo time.
9.Set a suitable distance threshold in the program.
10.If the measured distance is below the threshold, turn ON the LED.
11.If the measured distance is greater than the threshold, turn OFF the LED.
12.Start the simulation in Tinkercad and observe the LED operation while changing the ultrasonic sensor distance.
13.Verify that the digital output responds correctly to the measured distance.

# Algorithm:

1.Start
2.Initialize the ultrasonic sensor pins and LED pin.
3.Set the TRIG pin to LOW.
4.Generate a short HIGH pulse on the TRIG pin.
5.Read the duration of the signal received at the ECHO pin.
6.Calculate the distance from the echo duration.
7.Compare the measured distance with the predefined threshold.
8.If the distance is less than the threshold, turn ON the LED.
9.Otherwise, turn OFF the LED.
10.Display or monitor the measured distance.
11.Repeat the process continuously.
12.Stop

# program:

```c++
const int trigPin = 9;
const int echoPin = 10;

void setup() {
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  Serial.begin(9600);
}

void loop() {
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);
  
  long duration = pulseIn(echoPin, HIGH);
  int distance = duration * 0.0343 / 2; // Speed of sound wave divided by 2 (to and fro)
  
  Serial.print("Distance: ");
  Serial.print(distance);
  Serial.println(" cm");
  
  delay(500);
}
```
# OUTPUT:

<img width="1332" height="692" alt="image" src="https://github.com/user-attachments/assets/1f23bf8f-ce9b-4151-b769-11ed41caafc9" />
<img width="1919" height="822" alt="image" src="https://github.com/user-attachments/assets/869f6c28-30a2-433b-acef-462d2df1f0dd" />
<img width="1919" height="832" alt="image" src="https://github.com/user-attachments/assets/2278b9b9-5dac-4185-8771-ead275272894" />

# Result:

The ultrasonic sensor was successfully interfaced with the development board in Tinkercad Circuits. The distance of an object was measured using the HC-SR04 sensor, and the LED was successfully controlled as a digital output according to the measured distance. The simulation worked successfully and demonstrated distance-based digital output control.
