/*

  This is a simple demo of sending and receiving some data.
  Be sure to check out other examples!
*/

//Fill-in information from Blynk Device Info here
#define BLYNK_TEMPLATE_ID "TMPL6wNK5GaUO"
#define BLYNK_TEMPLATE_NAME "Is autopump"
#define BLYNK_AUTH_TOKEN "gn0qnsGgNBDI1ZVL3SC_FH3Mo6yi-j1C"

//Comment this out to disable prints and save space
#define BLYNK_PRINT Serial

#include <ESP8266WiFi.h>
#include <BlynkSimpleEsp8266.h>
#include <WiFiManager.h>
#define relay2 D2
#define relay1 D4
WiFiManager wm;
BLYNK_CONNECTED()
{
  Blynk.setProperty(V3, "offImageUrl", "https://static-image.nyc3.cdn.digitaloceanspaces.com/general/fte/congratulations.png");
  Blynk.setProperty(V3, "onImageUrl",  "https://static-image.nyc3.cdn.digitaloceanspaces.com/general/fte/congratulations_pressed.png");
}
BLYNK_WRITE(V0) {
  bool value3 = param.asInt();
  if (value3 == 1) {
    wm.resetSettings();
    for (int i = 5; i < 0; i--) {
      delay(1000);
    }
    wm.autoConnect("warittha");
    Blynk.config(BLYNK_AUTH_TOKEN);
  }
  else {}
}
BLYNK_WRITE(V1) {
  bool value = param.asInt();
  if (value == 1) {
    digitalWrite(relay1, LOW);
  }
  else {
    digitalWrite(relay1, HIGH);
  }
}
BLYNK_WRITE(V4) {
  bool value2 = param.asInt();
  if (value2 == 1) {
    digitalWrite(relay2, LOW);
  }
  else {
    digitalWrite(relay2, HIGH);
  }
}

void setup()
{
  Serial.begin(115200);
  for (int i = 5; i < 0; i--) {
    delay(1000);
  }
  wm.autoConnect("warittha");
  Blynk.config(BLYNK_AUTH_TOKEN);
  pinMode(relay1, OUTPUT);
  pinMode(relay2, OUTPUT);
}

void loop()
{
  Blynk.run();
}
