#### Basic Code for Doorbell

##### Upload #1 Doorbell

Upload the code #1 below. The example below uses the *5* and *6* digital pins. You can use any digital pin just remember to update the sketch.

```cpp
//If you use any different socket change them below
#define buttonSocket 5 // <- Socket for button
#define buzzerSocket 6// <- Socket for piezo buzzer

void setup()
{
  pinMode(buttonSocket, INPUT);
  pinMode(buzzerSocket, OUTPUT);
}

void loop()
{
  digitalWrite(buzzerSocket, digitalRead(buttonSocket));
}

```

##### Upload for #2 Doorbell

Upload the code #2 below. The example below uses the *5* and *6* digital pins. You can use any digital pin just remember to update the sketch.

```cpp
//If you use any different socket change them below
#define buttonSocket 5 // <- Socket for button
#define buzzerSocket 6// <- Socket for piezo buzzer

void setup()
{
  pinMode(buttonSocket, INPUT);
  pinMode(buzzerSocket, OUTPUT);
}

void loop()
{
  digitalWrite(buzzerSocket, digitalRead(buttonSocket));
}

```

```cpp

```
