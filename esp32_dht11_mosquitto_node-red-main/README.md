# Temperature and Humidity Monitoring

This project uses an ESP32 microcontroller and a DHT11 sensor to measure temperature and humidity. The collected data is sent to a Mosquitto MQTT broker and visualized using a Node-RED dashboard.

You can find out more about the course [here](https://www.ipportalegre.pt/pt/oferta-formativa/pos-graduacao-data-science-and-digital-transformation).

## Overview

This project enhances a simpler version that only supported local network communication without a dashboard. Now, with the integration of Node-RED, users can monitor and interact with sensor data via an intuitive interface.
Course: Internet of Things

## Hardware Requirements

- ESP32
- DHT11 Temperature and Humidity Sensor
- 10k Ohm resistor
- Breadboard
- Jumper wires

![image](https://github.com/user-attachments/assets/827ad802-566e-4a2f-8514-887fff1482b4)


## Software Requirements

- PlatformIO (preferred) or Arduino IDE
- Mosquitto MQTT Broker
- Node-RED

## Setup and Installation

There is a more detailed guide [here](ProjetoFinal_JoaoAlexArrudaDaSilva.pdf).

1. **Hardware Setup**: Connect the DHT11 sensor to your ESP32. The connections are as follows:

   - DHT11 VCC to ESP32 3V3
   - DHT11 GND to ESP32 GND
   - DHT11 DATA to ESP32 GPIO 4
   - DHT11 DATA to 10k Ohm resistor
   - 10k Ohm resistor to ESP32 3V3

   It should look something like this:
   ![ESP32 DHT11 Wiring](https://imgur.com/MiuOGkL.jpg)

2. **Software Setup**: 
   - Install and setup VSCode + PlatformIO (preferred) or Arduino IDE.
   - Install Mosquitto MQTT Broker.
   - Install Node-RED.
   - Install Node-RED Dashboard.

3. **Code Deployment**: Upload the provided code to your ESP32.

## Running the Project

1. Start the Mosquitto broker.
2. Start Node-RED and open the provided dashboard.
3. Power on the ESP32.

## MQTT Broker

Download and install the Mosquitto MQTT Broker from [here](https://mosquitto.org/download/).
You can start the broker with the default configuration by running `mosquitto` in the terminal.

## Node-RED

Download and install Node-RED from [here](https://nodered.org/docs/getting-started/local).
You can start Node-RED by running `node-red` in the terminal.

![Node-RED Flow](https://imgur.com/jv2cUAx.png)



## Node-RED Dashboard

Install the Node-RED Dashboard from [here](https://flows.nodered.org/node/node-red-dashboard).
You can access the dashboard by going to `http://localhost:1880/ui` in your browser.

![Node-RED Dashboard](https://imgur.com/XGUOuPg.png)

## Troubleshooting

Be sure to follow the hardware setup correctly. If you're using a different ESP32 board, the GPIO pins may be different.

Pay attention to the serial output of the ESP32. It's very useful for debugging.

![Serial Output](https://imgur.com/kPssBJ0.png)

In the mosquitto.conf file, be sure to set the `allow_anonymous` option to `true`.
Also set listener to `1883 0.0.0.0` as seen below.

![Mosquitto Config](https://imgur.com/OqW4wx4.png)

## Considerations

The DHT11 sensor is a basic, low-cost option. Consider using a higher-quality sensor for more accurate data.

For Linux users, the setup process is straightforward. Windows users may encounter additional challenges.

PlatformIO is recommended for its advanced features, including code completion and linting.

## Future Improvements
Integrate additional ESP32 devices to share data on the same MQTT broker.

Implement actions based on received data (e.g., control appliances like air conditioners or humidifiers).

Host the Mosquitto broker and Node-RED on a Raspberry Pi for a dedicated setup.

Use higher-quality sensors for improved reliability.

Extend the system to real-world applications, such as smart home automation.
