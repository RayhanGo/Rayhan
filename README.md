# Rayhan
// please give me credit if your trying to do something or copy this code. 
#include <Servo.h>

Servo turret1;
Servo turret2;

int X = A0;
int Y = A1;
int SW = 2;

void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  pinMode(SW, INPUT);

  turret1.attach(3);
  turret2.attach(4);
}

void loop() {
  // put your main code here, to run repeatedly:
  int hasilX = analogRead(X);
  int hasilY = analogRead(Y);
  int hasilSW = analogRead(SW);

  Serial.print("Nilai X = ");
  Serial.print(hasilX);
  Serial.print(", Nilai Y = ");
  Serial.print(hasilY);
  Serial.print(", Nilai SW = ");
  Serial.print(hasilSW);
  Serial.println(hasilSW);
  delay(100);

int cx = map(hasilX,0,1022,180,0);
int cy = map(hasilY,0,1022,180,0);

turret1.write(cx);
turret2.write(cy);
}
