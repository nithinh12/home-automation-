#define BLYNK_TEMPLATE_ID "TMPL3O5mSlg6n"
#define BLYNK_TEMPLATE_NAME "Smart Home"
#define BLYNK_AUTH_TOKEN "PyyC0iPgk41ul06hQuoYXeDzOqaflr8d"

#define BLYNK_PRINT Serial

#include <ESP8266WiFi.h>
#include <BlynkSimpleEsp8266.h>

char auth[] = BLYNK_AUTH_TOKEN;
  
char ssid[] = "Harsha's iPhone";
char pass[] = "tbtc5335";

BLYNK_WRITE(V0)
{
  int value = param.asInt();
  Serial.println(value);
  if(value == 1)
  {
    digitalWrite(D5, LOW);
    Serial.println("LED ON");
  }
  if(value == 0)
  {
     digitalWrite(D5, HIGH);
     Serial.println("LED OFF");
  }
}

BLYNK_WRITE(V1)
{
  int value = param.asInt();
  Serial.println(value);
  if(value == 1)
  {
    digitalWrite(D6, LOW);
    Serial.println("LED ON");
  }
  if(value == 0)
  {
     digitalWrite(D6, HIGH);
     Serial.println("LED OFF");
  }
}

BLYNK_WRITE(V2)
{
  int value = param.asInt();
  Serial.println(value);
  if(value == 1)
  {
    digitalWrite(D7, LOW);
    Serial.println("LED ON");
  }
  if(value == 0)
  {
     digitalWrite(D7, HIGH);
     Serial.println("LED OFF");
  }
}

BLYNK_WRITE(V3)
{
  int value = param.asInt();
  Serial.println(value);
  if(value == 1)
  {
    digitalWrite(D8, LOW);
    Serial.println("LED ON");
  }
  if(value == 0)
  {
     digitalWrite(D8, HIGH);
     Serial.println("LED OFF");
  }
}


void setup()
{
  Serial.begin(115200);
  Blynk.begin(auth, ssid, pass);
  pinMode(D5,OUTPUT);
  pinMode(D6,OUTPUT);
  pinMode(D7,OUTPUT);
  pinMode(D8,OUTPUT);
}

void loop()
{
  Blynk.run();
}
