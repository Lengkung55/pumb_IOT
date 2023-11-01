/*************************************************************

  This is a simple demo of sending and receiving some data.
  Be sure to check out other examples!
 *************************************************************/

/* Fill-in information from Blynk Device Info here */
#define BLYNK_TEMPLATE_ID "TMPL6asNaMmWH"
#define BLYNK_TEMPLATE_NAME "Quickstart Template"
#define BLYNK_AUTH_TOKEN "8NCtnIEEiDYvgsqtXpJAVB78gfx6iGkZ"

/* Comment this out to disable prints and save space */
#define BLYNK_PRINT Serial

#include <ESP8266WiFi.h> 
#include <BlynkSimpleEsp8266.h>

char ssid[] = "Gundam24";
char pass[] = "iB0837777995";
#define relay2 D2
#define relay1 D4
BLYNK_CONNECTED()
{
  Blynk.setProperty(V3, "offImageUrl", "https://static-image.nyc3.cdn.digitaloceanspaces.com/general/fte/congratulations.png");
  Blynk.setProperty(V3, "onImageUrl",  "https://static-image.nyc3.cdn.digitaloceanspaces.com/general/fte/congratulations_pressed.png");
  Blynk.setProperty(V3, "url", "https://docs.blynk.io/en/getting-started/what-do-i-need-to-blynk/how-quickstart-device-was-made");
}
BLYNK_WRITE(V1) {
  bool value = param.asInt();
  if (value == 1) {
    digitalWrite(relay1,LOW);
  }
  else {
    digitalWrite(relay1,HIGH);
  }
}
BLYNK_WRITE(V4) {
  bool value2 = param.asInt();
  if (value2 == 1) {
    digitalWrite(relay2,LOW);
  }
  else {
    digitalWrite(relay2,HIGH);
  }
}

void setup()
{
  Serial.begin(115200);
  Blynk.begin(BLYNK_AUTH_TOKEN, ssid, pass);
  pinMode(relay1,OUTPUT);
  pinMode(relay2,OUTPUT);
}

void loop()
{
  Blynk.run();
}
