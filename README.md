# YOMAN-
// MOTOR ARDUINO CODE FOR RC CAR

char t;
 
void setup() {
pinMode(11,OUTPUT);   //left motors forward
pinMode(10,OUTPUT);   //left motors reverse
pinMode(13,OUTPUT);   //right motors forward
pinMode(12,OUTPUT);   //right motors reverse

Serial.begin(9600);
 
}
 
void loop() {
if(Serial.available()){
  t = Serial.read();
  Serial.println(t);
}
 
if(t == 'F'){            //move forward(all motors rotate in forward direction)
  digitalWrite(11,HIGH);
  digitalWrite(13,HIGH);
}
 
else if(t == 'B'){      //move reverse (all motors rotate in reverse direction)
  digitalWrite(10,HIGH);
  digitalWrite(12,HIGH);
}
 
else if(t == 'L'){      //turn right (left side motors rotate in forward direction, right side motors doesn't rotate)
  digitalWrite(13,HIGH);
}
 
else if(t == 'R'){      //turn left (right side motors rotate in forward direction, left side motors doesn't rotate)
  digitalWrite(11,HIGH);



}
 
else if(t == 'S'){      //STOP (all motors stop)
  digitalWrite(11,LOW);
  digitalWrite(10,LOW);
  digitalWrite(13,LOW);
  digitalWrite(12,LOW);
}
delay(10);
}
