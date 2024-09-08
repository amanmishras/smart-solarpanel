#include<Servo.h>
int servoPin=8;
int lightVal;
int lightPin=A0;
int j;
int angle;
Servo myservo;
void setup() {
  
  
  myservo.attach(servoPin);
  pinMode(lightPin,INPUT);
  Serial.begin(9600);
}

void loop() {
  
  lightVal=analogRead(lightPin);
  Serial.println(lightVal);
  delay(500);
  angle=(-4/19.)*lightVal+4.*817./19.;
  myservo.write(angle);
    
}
