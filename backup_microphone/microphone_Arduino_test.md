This is the code used in Arduino IED for microphone used to detect gesture vibration.

```bash
# Separately
int ledPin = D2;
const int microphonePin = A0;

void setup() {
  Serial.begin(9600); // Missing semicolon added
  pinMode(ledPin, OUTPUT);
  // Optionally, you could add pinMode(microphonePin, INPUT); here for clarity
}

void loop() {
  int mn = 1024;
  int mx = 0;

  for (int i = 0; i < 100; ++i) {
    int val = analogRead(microphonePin);
    mn = min(mn, val);
    mx = max(mx, val);
  }

  int delta = mx - mn;

  Serial.println(delta); // Corrected function name and case

  if (delta > 200) {
    digitalWrite(ledPin, HIGH); // Corrected case
    delay(1000);
  } else {
    digitalWrite(ledPin, LOW); // Corrected case and added missing semicolon
  } // Added missing closing brace for the if statement block
}
```

```bash
# Combinition
int ledPin = D2;
const int microphonePin = A0;

void setup() {
  Serial.begin(9600); // Missing semicolon added
  pinMode(ledPin, OUTPUT);
  // Optionally, you could add pinMode(microphonePin, INPUT); here for clarity
}

void loop() {
  int mn = 1024;
  int mx = 0;

  for (int i = 0; i < 100; ++i) {
    int val = analogRead(microphonePin);
    mn = min(mn, val);
    mx = max(mx, val);
  }

  int delta = mx - mn;

  Serial.println(delta); // Corrected function name and case

  if (delta > 200) {
    digitalWrite(ledPin, HIGH); // Corrected case
    delay(1000);
  } else {
    digitalWrite(ledPin, LOW); // Corrected case and added missing semicolon
  } // Added missing closing brace for the if statement block
}
```