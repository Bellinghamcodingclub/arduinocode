#### Basic Code for Sound Sensor and Clapper

##### Upload for Sound Sensor

Upload the following code for the Sound Sensor. The example below uses the *A0* analog pin. You can use any of them just remember to update the sketch.

```cpp
//If you aren't using A0 as your socket change it below
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

##### Upload for Clapper

Upload the code below. This tutorial uses **Digital** socket 6. If you are using a different socket update the code after copying it. Set the `trigger` variable as that value you found from above.

```cpp
//If you aren't using A0 as your sound sensor socket change it below
#define soundSensorSocket A0

//If you aren't using pin 6 for your led socket change it below
#define ledSocket 6

int soundState;
int ledState;
int trigger = 600;

void setup()
{
  pinMode(ledSocket, INPUT);
  pinMode(ledSocket, OUTPUT);
}

void loop()
{
  if (analogRead(soundSensorSocket) > trigger) {
    soundState = 1;
  } else {
    soundState = 0;
  }

  ledState = digitalRead(ledSocket);
  if (ledState == 1 && soundState == 1) {
    delay(400);
    digitalWrite(ledSocket, LOW);
  }
  if (ledState == 0 && soundState == 1) {
    delay(400);
    digitalWrite(ledSocket, HIGH);
  }
}
```

```cpp

```
