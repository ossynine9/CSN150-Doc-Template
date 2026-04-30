# Cybersecurity : CSN150
Project: ESP32 XXXXXXXX

## Purpose
Set up ESP32 and Arduino enviornment. Execute sketch " Wifiscanner". 

## Equipment
* [ESP32Cam](https://www.amazon.com/Aideepen-ESP32-CAM-Bluetooth-ESP32-CAM-MB-Arduino/dp/B08P2578LV/ref=sr_1_3?crid=4FY0ECFW0ZX7&keywords=ESP32+Cam&qid=1678902050&sprefix=esp32+cam%2Caps%2C240&sr=8-3)

* [USB Micro Data Cable](https://www.amazon.com/AmazonBasics-Male-Micro-Cable-Black/dp/B0711PVX6Z/ref=sr_1_1_sspa?keywords=micro+usb+data+cable&qid=1678902214&sprefix=Micro+USB+data+%2Caps%2C89&sr=8-1-spons&psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUFaU0NaUVZHU1RFUlAmZW5jcnlwdGVkSWQ9QTA3NTA4MDVFVERCS01HVlgxM1YmZW5jcnlwdGVkQWRJZD1BMDE4NTE1NTIwWUdONkdWSzU1M1Amd2lkZ2V0TmFtZT1zcF9hdGYmYWN0aW9uPWNsaWNrUmVkaXJlY3QmZG9Ob3RMb2dDbGljaz10cnVl)

## Links to documentation and tools

##### Video 1: 

##### Other Links: 

##### AI GPTs used Chat GPT

## Steps I followed
Plugged in the ESP32-CAM but it was not detected at first
Installed the CH341SER driver so the computer could recognize the board
Selected "AI Thinker ESP32-CAM" as the board in Arduino IDE
Uploaded the CameraWebServer example code
First tried connecting ESP32 to WiFi using WiFi.begin()
Changed the code to make ESP32 act as a WiFi Access Point using WiFi.softAP()
Removed the WiFi connection loop and replaced it with Access Point code
Fixed coding errors like missing semicolons
Fixed wrong IP function (used WiFi.softAPIP instead of WiFi.localIP)
Uploaded code again and opened Serial Monitor to debug
Saw camera errors and checked configuration and hardware connections
## Problems and Solutions
Problem 1: ESP32-CAM WiFi not showing
Cause: Code was still trying to connect to WiFi instead of creating one
Solution: Replaced WiFi.begin() with WiFi.softAP() so ESP32 creates its own network

Problem 2: Compilation error ("expected ';' before Serial")
Cause: Missing semicolon
Solution: Added the semicolon to fix the syntax error

Problem 3: Wrong IP address function
Cause: Used WiFi.localIP() in Access Point mode
Solution: Changed to WiFi.softAPIP()

Problem 4: Camera not detected (Error 0x106)
Cause: Wrong camera config or loose connection
Solution: Set correct camera model (AI Thinker) and checked ribbon cable

Problem 5: ESP32 not detected by computer
Cause: Missing driver
Solution: Installed CH341SER driver and selected correct port
**Problem:** E (485) camera: Camera probe failed with error 0x105(ESP_ERR_NOT_FOUND)
Camera init failed with error 0x105
**Solution:**

### Example Problem
**Problem:** Arduino code will not load on ESP32 Cam.
**Solution:** Camera drivers were incorrect I needed to install the driver: [https://www.wch-ic.com/downloads/CH341SER_ZIP.html](https://github.com/martin-ger/esp32_nat_router).  I used file, "CH341SER.ZIP" and it worked.

## Final Report
In this project, I set up the ESP32-CAM using Arduino IDE and configured it to work as a WiFi Access Point. I ran into multiple issues like driver problems, code errors, WiFi configuration mistakes, and camera detection errors.

By troubleshooting step by step, I learned how to debug using the Serial Monitor, fix code errors, and understand the difference between connecting to WiFi and creating a WiFi network. I also learned how important both software and hardware setup is when working with devices like the ESP32-CAM.

Overall, this project helped me better understand IoT devices and how embedded systems communicate over networks.
