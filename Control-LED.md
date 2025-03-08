```
#define BLYNK_TEMPLATE_ID "YOUR_TEMPLATE_ID" //TEMPLATE_ID ของตนเอง
#define BLYNK_TEMPLATE_NAME "Quickstart Template"
#define BLYNK_PRINT Serial

#include <WiFi.h>
#include <WiFiClient.h>
#include <BlynkSimpleEsp32.h>

char auth[] = "YOUR_AUTH_TOKEN"; //auth token ของตนเอง
char ssid[] = "pears"; //ชื่อwifiที่ใช้
char pass[] = "kanyakorn"; //passwordที่ใช้

int relayPin = 13; // กำหนดขา 13 เป็นขาเอาต์พุต

BLYNK_WRITE(V0) // ใช้ Virtual Pin V0 ในการควบคุม
{
  int value = param.asInt(); // รับค่าจาก Blynk (0 หรือ 1)
  digitalWrite(relayPin, value); // ควบคุมขา 13 ตามค่าที่ได้รับ
}

void setup()
{
  Serial.begin(115200);
  pinMode(relayPin, OUTPUT); // กำหนดขา 13 เป็น output
  digitalWrite(relayPin, LOW); // ตั้งค่าเริ่มต้นเป็นปิด

  Blynk.begin(auth, ssid, pass);
}

void loop()
{
  Blynk.run();
}
```
