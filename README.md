char inchar;
String voice;

void setup() {
 
  Serial.begin(9600);

  pinMode(8, OUTPUT);
  pinMode(9, OUTPUT);
  pinMode(10, OUTPUT);
  pinMode(11, OUTPUT);
  pinMode(12, OUTPUT);
  digitalWrite(12, HIGH);
}


void loop() {

  if (Serial.available() > 0) {
    inchar = Serial.read();
    voice += inchar;
    voice.toUpperCase();
    Serial.println(voice);
  }

  if (inchar == '1')  // ON
  {
    digitalWrite(8, LOW);
    digitalWrite(9, HIGH);
    digitalWrite(10, LOW);
    digitalWrite(11, HIGH);
    inchar = "";
  }

  else if (inchar == '2')  // OFF
  {
    digitalWrite(8, HIGH);
    digitalWrite(9, LOW);
    digitalWrite(10, HIGH);
    digitalWrite(11, LOW);
    inchar = "";
  }

  else if (inchar == '3')  // OFF
  {
    digitalWrite(8, HIGH);
    digitalWrite(9, LOW);
    digitalWrite(10, LOW);
    digitalWrite(11, HIGH);
    inchar = "";
  }

  else if (inchar == '4')  // OFF
  {
    digitalWrite(8, LOW);
    digitalWrite(9, HIGH);
    digitalWrite(10, HIGH);
    digitalWrite(11, LOW);
    inchar = "";
  }

  else if (inchar == '0')  // OFF
  {
    digitalWrite(8, LOW);
    digitalWrite(9, LOW);
    digitalWrite(10, LOW);
    digitalWrite(11, LOW);
    inchar = "";
  }


  else if (inchar == '5')  // OFF
  {
    digitalWrite(12, LOW);
    inchar = "";
  }

  else if (inchar == '6')  // OFF
  {
    digitalWrite(12, HIGH);
    inchar = "";
  }
}
