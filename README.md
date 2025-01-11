Run a ESP Home Web Portal through Docker or the Home Assistant Add-On:
```
version: '3'
services:
  esphome:
    container_name: esphome
    image: ghcr.io/esphome/esphome
    volumes:
      - <MYPATH>/esphome/config:/config
      - /etc/localtime:/etc/localtime:ro
    privileged: true
    environment:
      - USERNAME=janes
      - PASSWORD=vh4F5UR4eDTz7R6dT2mZYGWf
      - TZ=Europe/Berlin
    restart: unless-stopped
    ports:
      - 6052:6052
```

Access the ESP Home Portal through the IP of your Docker host on port 6052 (e.g mydockerhost:6052).

Add a new device, press continue and enter a name for your configuration, for example: "My Voice Assistant".  
![image](https://github.com/user-attachments/assets/6835d4dd-0a2f-4cbb-8de4-33046be358fb)

Select "ESP32-S3" as your device type and then press "Skip":  
![image](https://github.com/user-attachments/assets/8deaf712-aa2e-4a1e-8d11-2d4153e19c9f)

In the dashboard a new device should be visible:  
![image](https://github.com/user-attachments/assets/6eafb97f-8105-410e-a301-5d07844e4765)

Press the "Edit" button and replace all the content of YAML file with content of the esp32-s3-box-3b.yaml of this repository:  
![image](https://github.com/user-attachments/assets/d385456c-2e7e-4856-acbd-a023f321c465)

Replace the two entries in the wifi section with your Wifi credentials:

```
wifi:
  ssid: "MYSSID" //REPLACE ME
  password: "MYWIFIPASSWORD" // REPLACE ME
``` 

After that press "Install" and use "Manual download":  
![image](https://github.com/user-attachments/assets/9e4fddb5-8d8d-48ed-8540-3b58bcd95d66)

Finally the build process starts and a dialog should be provided with the option to download an ESPHome Web Firmware file:  
![image](https://github.com/user-attachments/assets/a59aa20d-1beb-429e-a78b-bc8e33e89a20)

After you've downloaded the firmware file, move over to 
