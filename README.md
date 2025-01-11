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
      - USERNAME=randomuser
      - PASSWORD=randompassword
      - TZ=Europe/Berlin
    restart: unless-stopped
    ports:
      - 6052:6052
```

Access the ESP Home Portal through the IP of your Docker host on port 6052 (e.g mydockerhost:6052).

Add a new device, press continue and enter a name for your configuration, for example: "My Voice Assistant".  
![image](https://github.com/user-attachments/assets/a92ca5bf-82a9-458d-877c-943357aed547)
![image](https://github.com/user-attachments/assets/fb8acaed-4eff-4575-953c-8ec784db4ddf)

Select "ESP32-S3" as your device type and then press "Skip":  
![image](https://github.com/user-attachments/assets/f71673fe-1455-4125-a3f1-452d948a3392)

In the dashboard a new device should be visible:  
![image](https://github.com/user-attachments/assets/bb07dd9a-35f4-4306-ac66-8526468ac11e)

Press the "Edit" button and replace all the content of YAML file with content of the esp32-s3-box-3b.yaml of this repository:  
![image](https://github.com/user-attachments/assets/43889e33-394b-4a59-a58a-cb6ab48ec517)

Replace the two entries in the wifi section with your Wifi credentials:

```
wifi:
  ssid: "MYSSID" //REPLACE ME
  password: "MYWIFIPASSWORD" // REPLACE ME
``` 

After that press "Install" and use "Manual download":  
![image](https://github.com/user-attachments/assets/8931c23a-4d98-42d7-a794-59fc985c7985)

Finally the build process starts and a dialog should be provided with the option to download an ESPHome Web Firmware file:  
![image](https://github.com/user-attachments/assets/b8775a1b-bf86-4465-85e1-7c5ae621577a)

![image](https://github.com/user-attachments/assets/2adf5fac-33b6-497d-bc8c-0f70174c104e)

After you've downloaded the firmware file, move over to https://web.esphome.io/ and connect your device through the "CONNECT" button:  
![image](https://github.com/user-attachments/assets/4beaa8fd-b5de-49be-8ca1-9c6f9d39aee2)
Select the correct port, install and use the downloaded firmware file:
![image](https://github.com/user-attachments/assets/5163e716-3db7-4a5c-9e23-47f12a6c0ce3)
![image](https://github.com/user-attachments/assets/0809d486-b15d-484a-9f64-e7cfb8bdf05f)

Et voíla, all done.


