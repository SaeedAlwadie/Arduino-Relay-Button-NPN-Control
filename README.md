# Arduino-Relay-Button-NPN-Control
Arduino Relay Button NPN Control


1- Login to tinkercad

2-Work for Relay circuit

3-Writing code to operate the Relay circuit

```

int pinButton = 8;
int Relay = 2;
int stateRelay = LOW;
int stateButton;
int previous = LOW;
long time = 0;
long debounce = 100;


int stayON = 5000; //stay on for 5000 ms

void setup() {
  pinMode(pinButton, INPUT);
  pinMode(Relay, OUTPUT);
}

void loop() {
  stateButton = digitalRead(pinButton);  
  if(stateButton == HIGH && previous == LOW && millis() - time > debounce) {
    if(stateRelay == HIGH){
      digitalWrite(Relay, LOW);
    } else {

      
       digitalWrite(Relay, HIGH);
       delay(stayON);
       digitalWrite(Relay, LOW);
    }
    time = millis();
  }
  previous == stateButton;
}

```
