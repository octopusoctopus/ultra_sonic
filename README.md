# ultra_sonic
코코아팹에 있는거 배낌ㅋㅋ
```cpp
int trig = 8;
int echo = 9;

int led = 3;

void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  
  pinMode(trig, OUTPUT);
  pinMode(echo, INPUT);
  pinMode(led, OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
  
  digitalWrite(trig, LOW);
  digitalWrite(echo, LOW);
  delayMicroseconds(2);
  digitalWrite(trig, HIGH);
  delayMicroseconds(10);
  digitalWrite(trig, LOW);
 
  unsigned long duration = pulseIn(echo, HIGH);
 
  

  float distance = duration / 29.0 / 2.0;

  Serial.print(distance);
  Serial.println("cm");
 
  if (distance < 10) {
    digitalWrite(led, HIGH);
  }

  else {
    digitalWrite(led, LOW);
  }

  delay(200);
}
```
