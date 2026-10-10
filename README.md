# smart-irrigation

Waters a plant on its own. An ESP8266 reads soil moisture, turns a pump relay on when the soil is dry, and sends the readings to ThingSpeak. A DHT11 adds air temperature and humidity, and a small OLED shows the moisture on the spot.

Built in 2021.

## How it works

- Soil moisture is read as an analog value and mapped to a percentage.
- At 30% or below, the relay on pin D5 switches the pump on. Above 30%, it switches off.
- The DHT11 on pin D4 reads temperature and humidity.
- Each cycle posts moisture, temperature, humidity and pump state to ThingSpeak fields 1 to 4.
- The SSD1306 OLED shows the current moisture.

## Flash it

Open `smartirrigation.ino` in the Arduino IDE. You need the `ESP8266WiFi`, `DHT`, `Adafruit_GFX` and `Adafruit_SSD1306` libraries. Fill in your Wi-Fi name, Wi-Fi password and ThingSpeak write key where the placeholders are, then upload.
