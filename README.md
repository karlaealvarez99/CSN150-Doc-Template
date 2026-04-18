# Cybersecurity : CSN150 CameraWebServer Arduino Project

## Name of Project by Karla Alvarez
ESP32 Introduction

## Purpose
Set up ESP32 and Arduino enviornment. Execute sketch " CameraWebServer". 

## Equipment
* [ESP32Cam](https://www.amazon.com/Aideepen-ESP32-CAM-Bluetooth-ESP32-CAM-MB-Arduino/dp/B08P2578LV/ref=sr_1_3?crid=4FY0ECFW0ZX7&keywords=ESP32+Cam&qid=1678902050&sprefix=esp32+cam%2Caps%2C240&sr=8-3)

* [USB Micro Data Cable](https://www.amazon.com/AmazonBasics-Male-Micro-Cable-Black/dp/B0711PVX6Z/ref=sr_1_1_sspa?keywords=micro+usb+data+cable&qid=1678902214&sprefix=Micro+USB+data+%2Caps%2C89&sr=8-1-spons&psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUFaU0NaUVZHU1RFUlAmZW5jcnlwdGVkSWQ9QTA3NTA4MDVFVERCS01HVlgxM1YmZW5jcnlwdGVkQWRJZD1BMDE4NTE1NTIwWUdONkdWSzU1M1Amd2lkZ2V0TmFtZT1zcF9hdGYmYWN0aW9uPWNsaWNrUmVkaXJlY3QmZG9Ob3RMb2dDbGljaz10cnVl)

## Links to documentation

##### Video : https://youtu.be/4inE-n6kXSE?si=Lypd8axutqWwJNgk  
##### Link : https://lastminuteengineers.com/getting-started-with-esp32-cam/  

 


## Steps I followed
1. I began by installing Arduino into by Windows computer.
2. I connected my ESP32-CAM to my computer with the Micro Data cable and checked the connection on my Device Manager along with the port.
3. Once my Arduino IDE was instlled and setup, I chose the board I planned to work with on the IDE's list of board (AI Thinker ESP32-CAM) along with the port I plan to work with.  
- Opened Arduino IDE → **File** → **Preferences**
- Added this URL to **Additional Boards Manager URLs**:
https://espressif.github.io/arduino-esp32/package\_esp32\_index.json
- Went to **Tools** → **Board** → **Boards Manager**
- Searched for "**esp32**" and installed "**ESP32 by Espressif Systems**"
5. I loaded the CameraWebServer Example on Arduino.  
- **File** → **Examples** → **ESP32** → **Camera** → **CameraWebServer**  
- Modified WiFi credentials:  
const char* ssid = "YOUR\_WIFI\_SSID";  
const char* password = "YOUR\_WIFI\_PASSWORD";
5. I uncommented CAMERA_MODEL_AI_THINKER on the example documentation.
6. I uploaded the example and pressed the reset button on the ESP32.
7. I opened the Serial Monitor, and found the PI address link and opened it on the browser.  
8. I finally pressed the "Start Stream" button.


## Problems
Note your problems or errors here.  Google any error you may come across, and not what you tried (even if it does not work), and what was the final answer. Document your errors and solutions that worked for you.  

1. E (485) camera: Camera probe failed with error 0x105(ESP_ERR_NOT_FOUND)
Camera init failed with error 0x105
How did I solve:  
Root cause: Wrong camera model selected in code    
Solution: Ensured the correct camera model was uncommented  

 > #define CAMERA\_MODEL\_AI\_THINKER // Has PSRAM

Also checked that all other camera model definitions were commented out
Additional check: Verified camera ribbon cable was properly inserted  

2. Could not connect to WiFi / No IP address shown
Problem: Serial monitor showed "Connecting to WiFi..." indefinitely

Solution:
- Double-checked WiFi credentials (SSID and password)  
- Ensured WiFi is 2.4GHz (ESP32 doesn't support 5GHz)  
- Moved ESP32-CAM closer to router during initial testing  
- Verified no special characters in password that might cause issues  


## Final Report  

I successfully configured the ESP32-CAM as a web server, and I achieved live video streaming over a local Wifi network with an accessible web interface. For future improvements, I hope to integrate this project into a home automation system along with motion detection functionality.  



