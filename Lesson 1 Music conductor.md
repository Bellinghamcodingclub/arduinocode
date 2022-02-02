

##### Baisc Code for Bit Music Conductor

Upload the code below. This tutorial uses **Digital** socket 6. If you are using a different socket update the code after copying it.

```cpp
//Change here if you're using a different socket
#define buzzerSocket 6

int length = 15; // the number of notes
char notes[] = "ccggaagffeeddc "; // a space represents a rest
int beats[] = { 1, 1, 1, 1, 1, 1, 2, 1, 1, 1, 1, 1, 1, 2, 4 };
int tempo = 300;

void setup() {
  pinMode(buzzerSocket, OUTPUT);

  for (int i = 0; i < length; i++) {
    if (notes[i] == ' ') {
      delay(beats[i] * tempo); // rest
    } else {
      playNote(notes[i], beats[i] * tempo);
    }

    // pause between notes
    delay(tempo / 2);
  }
}

void loop() {

}

void playTone(int tone, int duration) {
  for (long i = 0; i < duration * 1000L; i += tone * 2) {
    digitalWrite(buzzerSocket, HIGH);
    delayMicroseconds(tone);
    digitalWrite(buzzerSocket, LOW);
    delayMicroseconds(tone);
  }
}

void playNote(char note, int duration) {
  char names[] = { 'c', 'd', 'e', 'f', 'g', 'a', 'b', 'C' };
  int tones[] = { 1915, 1700, 1519, 1432, 1275, 1136, 1014, 956 };

  // play the tone corresponding to the note name
  for (int i = 0; i < 8; i++) {
    if (names[i] == note) {
      playTone(tones[i], duration);
    }
  }
}

```





Below are some pretty well known melodies to get you started. Replace the block of code that contains these variables in the example above.

##### Ode to Joy

```cpp
//All the code to make a song is in this block
int length = 15; // the number of notes
char notes[] = "eefggfedccdeedd"; // a space represents a rest
int beats[] = { 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 2, 1, 1 };
int tempo = 300;
```

##### Super Mario Brothers

```cpp
//All the code to make a song is in this block
int length = 8; // the number of notes
char notes[] = "eeecegc"; // a space represents a rest
int beats[] = { 1, 1, 2, 1, 1, 4, 1};
int tempo = 120;
```
