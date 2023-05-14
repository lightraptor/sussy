| Supported Targets | ESP32 | ESP32-C3 | ESP32-S2 | ESP32-S3 |
| ----------------- | ----- | -------- | -------- | -------- |

# ESP-MQTT SSL Sample application

(See the README.md file in the upper level 'examples' directory for more information about examples.)

This example connects to the broker mqtt.eclipseprojects.io using ssl transport and as a demonstration subscribes/unsubscribes and send a message on certain topic.
(Please note that the public broker is maintained by the community so may not be always available, for details please see this [disclaimer](https://iot.eclipse.org/getting-started/#sandboxes))

It uses ESP-MQTT library which implements mqtt client to connect to mqtt broker.

## How to use example

### Hardware Required

This example can be executed on any ESP32 board, the only required interface is WiFi and connection to internet.

### Configure the project

* Open the project configuration menu (`idf.py menuconfig`)
* Configure Wi-Fi or Ethernet under "Example Connection Configuration" menu. See "Establishing Wi-Fi or Ethernet Connection" section in [examples/protocols/README.md](../../README.md) for more details.

PEM certificate for this example could be extracted from an openssl `s_client` command connecting to mqtt.eclipseprojects.io.
In case a host operating system has `openssl` and `sed` packages installed, one could execute the following command to download and save the root certificate to a file (Note for Windows users: Both Linux like environment or Windows native packages may be used).
```
echo "" | openssl s_client -showcerts -connect mqtt.eclipseprojects.io:8883 | sed -n "1,/Root/d; /BEGIN/,/END/p" | openssl x509 -outform PEM >mqtt_eclipse_org.pem
```
Please note that this is not a general command for downloading a root certificate for an arbitrary host;
this command works with mqtt.eclipseprojects.io as the site provides root certificate in the chain, which then could be extracted
with text operation.

### Build and Flash

Build the project and flash it to the board, then run monitor tool to view serial output:

```
idf.py -p PORT flash monitor
```

(To exit the serial monitor, type ``Ctrl-]``.)

See the Getting Started Guide for full steps to configure and use ESP-IDF to build projects.

## đây là demo 
hình minh hoạ demo sử dụng port 8883 connect với broker của hivemq 
![8883_02](https://github.com/lightraptor2310/sussy/assets/75661466/a77440dc-a559-42f6-ac11-0b856d5cb8eb) 
![8883_03](https://github.com/lightraptor2310/MQTT_esp32_port1883/assets/75661466/50c76b13-93c8-49f1-88c6-6c7743ef5a02)

