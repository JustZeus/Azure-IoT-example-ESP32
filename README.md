# Azure-IoT-example-ESP32
 Modified example: "iothub_II_telemetry_sample" of the Azure IoT libraries for the arduino framework, with an ESP32 development board, BME280 and BH1750 light sensors. 
 ## Getting Ready 🚀

_This example will allow you to send and recieve telemetry to/from an Azure IoT hub, telemetry is sent periodically according to a time interval modifiable by the user, using the C language SDK adapted for the ESP32 microcontroller, the libraries that adapt the SDK to the arduino framework are officially provided by Microsoft._

### Pre-requirements 📋

1. Have Visual Studio Code installed with the PlatformIO IDE extension: <br>
 _Check Visual Studio Code here:_ [VS Code](https://code.visualstudio.com/) <br>
  _Check PlatformIO extension for VS Code Here:_ [PlatformIO](https://platformio.org/platformio-ide/) <br>
2. An ESP32 based development board
3. BME280 I2C Sensor module
4. BH1750 I2C Sensor module
5. LEDS and Resistors _(Optional)_
## Configurations ⚙️

Remember that you must provision your device connection String, same as you get from Azure IoT Hub / IoT Central services.

In the iot_configs.h file:

```
#define DEVICE_CONNECTION_STRING "your IoT Hub connection String"
```
As well you must provide the name and password of your network:
```
#define IOT_CONFIG_WIFI_SSID "Your network's name"
#define IOT_CONFIG_WIFI_PASSWORD "Your network's Password"
```

Finally, to communicate with a serial terminal, this configuration is provided, it can be modified according to your preferences:

In the platformio.ini file:
```
monitor_speed = 115200
```
In the sample_init.cpp file
```
static void initSerial()
{
    // Start serial and initialize stdout
    Serial.begin(115200);
    Serial.setDebugOutput(true);
}
```
## Circuit 🖇️

The circuit simply consists of feeding the boards with power and wiring the pins for I2C communication, Leds with resistors can be added in the 15, 4, 5 Pins.<br>
For the  Espressif ESP32 Dev Module: <br>

_Pin 21 for SDA_ <br>
_Pin 22 for SCL_ <br>

Example circuit assemble:
![Texto alternativo](https://rzstorage.blob.core.windows.net/video/202012111645572654284723398.jpg)

## Deployment 📦
As an example of use, a Azure IoT central app was provided to observe the variables graphically <br>



![Texto alternativo](https://rzstorage.blob.core.windows.net/video/ESP32-Azure_IoT_Central-1.jpg)

Learn for free how to deploy an app in Azure IoT Central app in Microsoft Learn:

[CreateYourFirstAzureIoTCentralApp](https://docs.microsoft.com/en-us/learn/modules/create-your-first-iot-central-app/)