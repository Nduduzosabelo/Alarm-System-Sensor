# Alarm-System-Sensor
# Create Alarm System Using Buzzer and Ultrasonic Sensor
* [Instructions](#Instructions)
* [Write code](#Write code)

<a name = "Instrucion"></a>
## Instructions
Setup power supply by connecting one end of a jumper wire to 5v pin of the Arduino Uno and the other to the "+" on the breadboard.

Connect another wire to the GND pin on the uno and the "-" of the breadboard.

Connect the positive side of the buzzer to the digital pin 2 of the Arduino Uno.

Connect the negative side of the buzzer to the "-" on the breadboard.

Connect the Vcc terminal of thed ultrasonic sensor to "+" on the breadboard.

Connect the GND of the sensor to the "-" on the breadboard.

Connect the trig pin to digital pin 10 on Arduino.

Connect the echo pin to digital pin 9

<a name = "Write code"></a>
## Write Code
On the arduino IDE open a new sketch: File>New...

At the top, declare variables by including the following:

int const trigPin = 10;
int const echoPin = 9;
int const buzzPin = 2;

In the void setup section write the following:
pinMode(trigPin, OUTPUT);
pinMode(echoPin, INPUT);
pinMode(buzzPin, OUTPUT);

In the void loop section add the following:
int distance, duration;
digitalWrite(trigPin, HIGH);
delay(1);
delayWrite(trigPin, LOW);
duration = pulseIn(echoPin, HIGH);
distance = (duration/2)/29.1;
if (distance <= 50 && distance >=0){
digitalWrite(buzzPin, HIGH);
} else {
digitalWrite(buzzPin, LOW);
}
delay(60);
