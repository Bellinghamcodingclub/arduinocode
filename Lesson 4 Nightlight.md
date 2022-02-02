##### Upload Code #1 for Nightlight

Upload the code #1 below. This tutorial uses Analog socket A0. If you are using a different socket, update the code after copying it.

```cpp
//Change here if you're using a different socket
#define sensorSocket A0

int val;

void setup() {
  Serial.begin(9600);
}

void loop() {
  val = analogRead(sensorSocket);
  Serial.println(val);
}

```

##### Upload #2 for Nightlight

Upload the code #2 below. This tutorial uses **Digital** socket 6. If you are using a different socket, update the code after copying it.

```cpp
#define ledSocket 6

int i;
int fadeTime = 50;

void setup()
{

}

void loop()
{
  for (i = 0; i <= 255; i++) {
    analogWrite(ledSocket, i);
    delay(fadeTime);
  }
  for (i = 255; i >= 0; i--) {
    analogWrite(ledSocket, i);
    delay(fadeTime);
  }
}

```

##### Upload #3 for Nightlight

Upload the code shown below. This tutorial uses **Digital** socket 5. If you are using a different socket, update the code after copying it.

```cpp
//If you use different socket numbers update them below
#define buttonSocket 5
#define ledSocket 6

void setup()
{
  pinMode(buttonSocket, INPUT);
  pinMode(ledSocket, OUTPUT);
}

void loop()
{
  if (digitalRead(buttonSocket)) {
    digitalWrite(ledSocket,HIGH);
  } else {
    digitalWrite(ledSocket,LOW);
  }
}

```

##### Upload #4 for Nightlight

Upload the code #4 shown below. Add in the covered light value from earlier in the `lowTrigger` variable. Add in the uncovered light value from earlier in the `highTrigger` variable.

```cpp
//If you use different socket numbers update them below
#define ledSocket 6
#define lightSensorSocket A0

int lowTrigger = 250;  //<- Change to YOUR measured value
int highTrigger = 300; //<- Change to YOUR measured value
int lightAmount;
int state;

void setup()
{
  pinMode(ledSocket, OUTPUT);
}

void loop()
{
  lightAmount = analogRead(lightSensorSocket);
  if (lightAmount < lowTrigger) {
    state = 1;
  } if (lightAmount > highTrigger) {
    state = 0;
  }

  if (state) {
    digitalWrite(ledSocket, HIGH);
  } else {
    digitalWrite(ledSocket, LOW);
  }
}

```
