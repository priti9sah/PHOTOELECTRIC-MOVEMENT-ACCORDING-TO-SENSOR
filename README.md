# PHOTOELECTRIC-MOVEMENT-ACCORDING-TO-SENSOR
The purpose of the project is to design a model in such a way that when a person will enter the room the lights will be turned on and when the person will leave the room the lights will be turned off.

#define trigPin 13
#define echoPin 12
#define led 11;
void setup() 
{
  Serial.begin(9600);
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  pinMode(led, OUTPUT);
}

void loop() 
{
 long duration=0, distance=0;
 digitalWrite(trigPin, LOW);
 delayMicroseconds(2);
 digitalWrite(trigPin, HIGH);
 delayMicroseconds(10);
 digitalWrite(trigPin, LOW);
 
 duration = pulseIn(echoPin, HIGH);
 distance =  (duration * 0.0340)/2;
 if(distance<10)
 {
 digitalWrite(led, HIGH);
}
else
{
  digitalWrite(led, LOW);
}
Serial.print(distance);
delay(100);
}

