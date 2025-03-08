```
#define LED_PIN 13  // กำหนดขา GPIO ที่ใช้ต่อ LED 

void setup() {
  pinMode(LED_PIN, OUTPUT);  // กำหนดให้ขา LED เป็นเอาต์พุต
}

void loop() {
  digitalWrite(LED_PIN, HIGH);  // เปิด LED
  delay(1000);                 // รอ 1 วินาที
  digitalWrite(LED_PIN, LOW);   // ปิด LED
  delay(1000);                 // รอ 1 วินาที
}

```
