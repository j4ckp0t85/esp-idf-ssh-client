# esp-idf-ssh-client
ssh client for esp-idf.   
This project use [this](https://github.com/libssh2/libssh2) ssh library.   

# Software requirements
esp-idf v4.4 or later.   
This is because this version supports ESP32-C3.   

# Installation

```
git clone https://github.com/nopnop2002/esp-idf-ssh-client
cd esp-idf-ssh-client/
git clone https://github.com/libssh2/libssh2 components/libssh2
cp esp-idf/libssh2_config.h components/libssh2/include
cp esp-idf/CMakeLists.txt components/libssh2
idf.py set-target {esp32/esp32s2/esp32c3}
idf.py menuconfig
idf.py flash
```


# Configuration   
You have to set this config value with menuconfig.   
- CONFIG_ESP_WIFI_SSID   
SSID (network name) to connect to.
- CONFIG_ESP_WIFI_PASSWORD   
WiFi password (WPA or WPA2) to use.
- CONFIG_ESP_MAXIMUM_RETRY   
Set the Maximum retry to avoid station reconnecting to the AP unlimited when the AP is really inexistent.
- CONFIG_SSH_USER   
Username of SSH.
- CONFIG_SSH_PASSWORD   
Password of SSH.
- CONFIG_SSH_HOST   
IP address of SSH host.   
__mDMS name cannot be used.__   
- CONFIG_SSH_PORT   
TCP port number 22 is used by default.   

![config-main](https://user-images.githubusercontent.com/6020549/120054821-3d755500-c06d-11eb-950c-d357d0a9fdef.jpg)
![config-app](https://user-images.githubusercontent.com/6020549/131051283-5614e66d-2c3a-4df7-88f2-863d3bf23b34.jpg)

# ssh command list   
ssh command list is defined ssh/command.txt.
```
$ cat ssh/command.txt
uname -a
ls -l
```


# Screen Shot
![ssh-client-1](https://user-images.githubusercontent.com/6020549/120056024-b1ffc200-c074-11eb-8507-1bb566b0cc7c.jpg)

# Reference
https://github.com/nopnop2002/esp-idf-scp-client

You can use scp and ssh to do heavy processing that esp32 alone cannot.  
- Execute server-side command with ssh.   
- Output the processing result to a file.   
- Copy file from server using scp-get.   


