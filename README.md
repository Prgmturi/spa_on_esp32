# Single Page Application on ESP32

## Description:
The  project provides a solution to host a Single Page Application (SPA) and makes an ESP32 microcontroller available as an mDNS webserver. This enables users to access the interactive content via a web browser, either by using the
"www.esp-home.local" URL if connected to the same network or through the local IP address of the ESP32 device when connected to the access point it creates.

## Key Features:

- Spa Web Server: The ESP32 microcontroller acts as a web server to host a Single Page Application (SPA), allowing users to access the content interactively through a web browser.
- Simplified Access: By implementing mDNS, accessing the services offered by the microcontroller becomes extremely straightforward. Users can use the "www.esp-home.local" URL to access the SPA, eliminating the need to know the specific IP address of the device.
- Access Point Mode: The ESP32 microcontroller can also function as an access point (AP), creating a local WiFi network for users to connect to and access the SPA. In this case, access is through the local IP address of the ESP32 device.

## Configuration 
To start and load the project into the ESP32 microcontroller, follow these steps:

- Configure Parameters in menuconfig: Use the menuconfig command to access the configuration menu. Set the necessary parameters for the project, ensuring they match your specific setup:
  SoftAP Configuration
WiFi AP SSID: Set the SSID (network name) for the Access Point (AP) created by the ESP32 microcontroller. This is the name users will see when connecting to the ESP32's network.

WiFi AP Password: Define the WiFi password for the AP. This password restricts access to the ESP32's AP.

WiFi AP Channel: Specify the WiFi channel (network channel) to be used by the AP.

Maximal STA Connections: Set the maximum number of allowed STA (Station) connections to the AP. This controls how many devices can connect to the ESP32 AP simultaneously.

STA Configuration
WiFi Remote AP SSID: Provide the SSID (network name) of the external WiFi network that the ESP32 microcontroller will connect to.

WiFi Remote AP Password: Enter the WiFi password for the remote network to facilitate ESP32's connection.

Maximum retry: Define the maximum number of connection attempts the ESP32 will make when connecting to the remote WiFi network. This prevents continuous reconnection attempts in cases where the remote AP doesn't exist.

WiFi Scan Auth Mode Threshold: Choose the weakest authmode to accept during the scan mode. The selection depends on the security settings of the remote AP. Options include OPEN, WEP, WPA PSK, WPA2 PSK, WPA/WPA2 PSK, WPA3 PSK, and WPA2/WPA3 PSK.

mDNS Configuration
mDNS Host Name: Specify the domain name used for the mDNS service. This allows access to the ESP32 device through a user-friendly domain name, such as "www.esp-home.local."

#### NOTE: To Allow your esp32 read the chunked file you must avoid using /static in your website build folder. The maximum name length for a file 31.
    Go to webpack.config.js and change all the output (css,js and media) directory from /static/path/chunk to /path/chunk
    for example from static/js/12345has.chunk.js to  js/12345hash.chunk.js

- Build and Upload the SPIFFS Image: Before building the firmware, create an image of the SPIFFS filesystem.
- Build the Firmware: Build the firmware for the ESP32.

## Usage:
Once the project is configured and uploaded to the ESP32 microcontroller, visitors can access the SPA by entering the "www.esp-home.local" URL in their web browser, or by connecting to the Access Point created by the device and using the provided local IP address.
This project is particularly useful for creating multi-operating system (multios) user interfaces, as it allows access to the SPA content from any web browser, simplifying interaction with the ESP32 microcontroller.

## Note:

