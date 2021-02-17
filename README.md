## Decoding Random Bluetooth Address of IOS 
To protect the private, Bluetooth 4.0 Low Energy usually to do advertising with a random private address. <br>
<br>
The private address may be of either of the following two sub-types: <br>
• Non-resolvable private address<br>
• Resolvable private address<br>
<br>
A resolvable private address may be resolved if the corresponding device’s IRK is available using this procedure. If a resolvable private address is resolved, the device can associate this address with the peer device. <br>

When IOS is enabling with continuity service, it will always sending BLE advertising to let other IOS device to know. Of course, the Bluetooth MAC Address is random and changed every 15 minutes. <br>

But this random address is a Resolvable private address. If the IRK of this IOS device is known, the random address can be determined if it belongs to this device. <br>

## Get IRK of your iPhone
Use an ESP32 board and download with “get_irk” project. It will start a BLE service. <br>
Pay attention on following settings.<br>
![](https://github.com/fryefryefrye/Bluetooth-keyless-system/raw/master/img/arduino_setting.jpg) <br>
Use your iPhone install with “LightBlue” APP, find the “ESP_BLE_SECURITY” service, and connect it, the IRK will be print out. <br>
![](https://github.com/fryefryefrye/Bluetooth-keyless-system/raw/master/img/get_irk.jpg) <br>

## Monitor BLE advertising with nRF24L01
With the help of the following project, we can Monitor BLE advertising with very cheap nRF24L01 module<br>
https://github.com/Pranavgulati/RF24BLE<br>
https://github.com/nRF24/RF24<br>
Install above two library into Arduino.<br>
Download “nrf_ble_add” project into a Arduino nano board, you can Monitor BLE advertising and determine if the MAC address in the air is belong to your iPhone.<br><br>
These is only one key function you need to call to check MAC address. Everything needed for this function is in key.h file.You can use it in your other project.<br>
BOOLEAN btm_ble_addr_resolvable(BD_ADDR rpa, esp_bt_octet16_t irk)<br><br>

You can build the Arduino based BLE Monitor Just connect nRF24L01 module with Arduino follow the table.<br>

![](https://github.com/fryefryefrye/Bluetooth-keyless-system/raw/master/img/uno_nrf.jpg) <br>

![](https://github.com/fryefryefrye/Bluetooth-keyless-system/raw/master/img/ResolveAddress.jpg) <br>

## Reference
Most of the code is copied and pasted from the following project.Great Thanks to this great company and their amazing ESP32 module with source code.<br>
https://github.com/espressif/esp-idf <br>



