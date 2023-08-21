#define BLYNK_TEMPLATE_ID "TMPL3J0fje7Ap"
#define BLYNK_TEMPLATE_NAME "distance measurement"
#define BLYNK_AUTH_TOKEN "0gkBRNdSe6_dnOv5ySxaEggiUd-9iRmX"

#include <Wire.h>
#include <WiFi.h>
#include <BlynkSimpleEsp32.h>

// Rest of your code remains the same...


#define echoPin 2
#define trigPin 4
long duration, distance;

char auth[] = "0gkBRNdSe6_dnOv5ySxaEggiUd-9iRmX";
char ssid[] = "Apeed";         // Replace with your Wi-Fi SSID
char pass[] = "CLB356D618";     // Replace with your Wi-Fi password

void setup() {
  Serial.begin(9600);
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  
  Blynk.begin(auth, ssid, pass);
}

void loop() {
  Blynk.run();
  
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);
  
  duration = pulseIn(echoPin, HIGH);
  distance = duration / 58.2;
  
  Blynk.virtualWrite(V0, distance);
  
  Serial.print("Distance: ");
  Serial.print(distance);
  Serial.println(" cm");
  
  delay(1000);
}
