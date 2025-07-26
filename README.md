int pirPin = 2;
int ledPin = 13;
int motionState = LOW;

void setup() {
  pinMode(pirPin, INPUT);
  pinMode(ledPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  motionState = digitalRead(pirPin);

  if (motionState == HIGH) {
    digitalWrite(ledPin, HIGH);
    Serial.println("Motion detected!");
    delay(3000); // LED stays on for 3 seconds
  } else {
    digitalWrite(ledPin, LOW);
  }
}
