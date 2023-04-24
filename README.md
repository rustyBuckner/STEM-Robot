# STEM-Robot
int enA = 5; 
int enB = 6;
int in1 = 9;
int in2 = 8;
int in3 = 10;
int in4 = 7;
int trig = 2;
int echo = 3;
long duration;
int distance;


void setup() {
  pinMode(enA, OUTPUT);
  pinMode(enB, OUTPUT);
  pinMode(in1, OUTPUT);
  pinMode(in2, OUTPUT);
  pinMode(in3, OUTPUT);
  pinMode(in4, OUTPUT);
  
  analogWrite(enA, 180);
  analogWrite(enB, 180);
  
}

void loop() {
  digitalWrite(trig,LOW);
  delayMicroseconds(2);
  digitalWrite(trig,HIGH);
  delayMicroseconds(10);
  digitalWrite(trig,LOW);
  duration = pulseIn(echo,HIGH);
  distance = duration * 0.035/2;
  Serial.print("Distance:");
  Serial.println(distance);
  if (distance > 40){
  Forward();
  delay(500);
  }
  else {
  Stop();
  delay(500);
  Backward();
  delay(1000);
  Left();
  delay(1000);
  }
}



void Forward(){
digitalWrite(in1, HIGH);
digitalWrite(in2, LOW);
digitalWrite(in3, LOW);
digitalWrite(in4, HIGH);
}

void Left(){
digitalWrite(in1, LOW);
digitalWrite(in2, HIGH);
digitalWrite(in3, LOW);
digitalWrite(in4, HIGH);
}


void Backward(){
digitalWrite(in1, LOW);
digitalWrite(in2, HIGH);
digitalWrite(in3, HIGH);
digitalWrite(in4, LOW);
}

void Stop(){
digitalWrite(in1, LOW);
digitalWrite(in2, LOW);
digitalWrite(in3, LOW);
digitalWrite(in4, LOW);
}




