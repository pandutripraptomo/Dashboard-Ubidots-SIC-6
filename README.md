# Dashboard-Ubidots-SIC-6

📊 Real-Time Sensor Monitoring Dashboard with Ubidots
Welcome to the Real-Time Sensor Monitoring Dashboard project! In this IoT (Internet of Things) system, an Ultrasonic Sensor and DHT11 Sensor are used to collect real-time environmental data, which is then visualized on a custom dashboard hosted on Ubidots. Data transmission is handled using the MQTT protocol, ensuring seamless, real-time updates for continuous monitoring.

📌 Overview
This project uses two key sensors to collect environmental data:

Distance Measurement: Using an Ultrasonic Sensor (HC-SR04), the system measures the distance of objects in the environment. This can be used for a variety of applications, including liquid level detection, proximity monitoring, or object tracking.

Temperature and Humidity Monitoring: The DHT11 Sensor reads ambient temperature and humidity values. These parameters are crucial for applications in weather monitoring, climate control systems, and indoor environment monitoring.

The collected sensor data is sent to the Ubidots platform, where it is displayed in real-time. The MQTT protocol is used to ensure efficient communication between the microcontroller and Ubidots. This project provides an excellent demonstration of how IoT devices can be integrated into a cloud-based platform for monitoring and analysis.

🔧 Features
Ultrasonic Distance Measurement:

Accurately measures the distance of objects in real time. Ideal for proximity detection and level monitoring applications.
The sensor emits sound waves and calculates the time it takes for the waves to reflect back, allowing for precise distance measurements.
Temperature and Humidity Tracking:

The DHT11 sensor provides reliable temperature and humidity readings.
This is ideal for creating systems for climate control, environmental monitoring, and smart building management.
Real-Time Data Visualization on Ubidots:

The data from both sensors is pushed to Ubidots, where it is displayed on a real-time dashboard.
With widgets like gauges, graphs, and charts, the data is easy to interpret, providing insights into the monitored environment.
Lightweight Communication with MQTT:

The system utilizes MQTT, a lightweight protocol designed for IoT. This allows the system to handle frequent data updates while using minimal network bandwidth and power.
MQTT is especially well-suited for real-time monitoring systems where efficiency and speed are crucial.
🛠️ Required Hardware
Microcontroller: Choose a Wi-Fi-enabled board (e.g., ESP32, ESP8266, or similar).
Ultrasonic Sensor (HC-SR04):
Measures the distance to an object using sound waves.
Consists of a Trigger Pin and an Echo Pin for sending and receiving the signal.
DHT11 Temperature and Humidity Sensor:
Measures temperature (°C) and humidity (%) in the surrounding environment.
Power Supply: The microcontroller and sensors are powered via a 5V or 3.3V supply depending on the board used.
⚙️ Setup Instructions
Follow these steps to set up the project:

1. Hardware Connections:
Ultrasonic Sensor (HC-SR04):
TRIG pin → GPIO 22
ECHO pin → GPIO 23
DHT11 Sensor:
Connect the VCC pin to 5V or 3.3V depending on the microcontroller.
Connect the GND pin to Ground.
Connect the DATA pin to GPIO 13 (or another GPIO pin of your choice).
2. Install Dependencies:
You’ll need to install libraries for:

DHT11 Sensor (usually comes with the Adafruit DHT library or dht library in MicroPython).
MQTT Library (Use umqtt.simple or MQTT library for microcontrollers).
3. Configure Wi-Fi:
Edit the SSID and PASSWORD fields in the script to match your Wi-Fi credentials.

4. Set Up Ubidots:
Create an account on Ubidots and set up a new Device.
Replace the [device_name] in the Ubidots URL with your actual device name.
Obtain your Ubidots API Token from the dashboard and add it to the script.
5. Upload the Code:
Upload the Python script to your microcontroller using an IDE like Thonny (for MicroPython) or Arduino IDE.
Run the script to start sending sensor data to Ubidots.
🔄 How It Works
Wi-Fi Connection:
The microcontroller connects to your local Wi-Fi network using the provided SSID and PASSWORD credentials.
Sensor Data Collection:
The Ultrasonic Sensor (HC-SR04) emits sound pulses from the TRIG pin. The time it takes for the pulse to return to the ECHO pin is measured, and the distance is calculated using the formula:
Distance (cm)
=
Pulse Duration
×
0.0343
2
Distance (cm)= 
2
Pulse Duration×0.0343
​
 
The DHT11 Sensor measures the ambient temperature and humidity values using the digital signal from the DATA pin.
Data Transmission:
The collected data (distance, temperature, and humidity) is sent to Ubidots using HTTP POST requests every 10 seconds.
The data is packaged in a JSON format, with each value mapped to specific variables (e.g., distance, temperature, humidity).
Data Visualization:
Ubidots receives the data and visualizes it in real time:
Temperature and Humidity are displayed on gauge widgets.
Distance is shown on a line graph, making it easy to track changes over time.
📊 Data Visualization Example
Once the data is uploaded to Ubidots, you can visualize:

Temperature: A real-time gauge displaying the current temperature.
Humidity: A gauge showing the current humidity level.
Distance: A line graph representing the changes in distance over time.
📈 Sample Output
Example data being collected:

Temperature: 25°C
Humidity: 60%
Distance: 10 cm (values fluctuate as objects move closer or farther)
🔧 Customization
You can expand this project by:

Adding More Sensors: Integrate additional sensors (e.g., gas sensors, motion sensors) for a more comprehensive environmental monitoring system.
Advanced Visualization: Use advanced widgets like charts, maps, or historical data graphs in Ubidots for deeper analysis.
Mobile Integration: Integrate the system with mobile apps to send notifications or trigger actions based on sensor data.
⚠️ Troubleshooting
No Wi-Fi Connection: Ensure the credentials are correct and check if the microcontroller is within Wi-Fi range.
Data Not Displaying on Ubidots: Double-check the device name and API token in the script.
Sensor Not Reading Correctly: Make sure the sensors are wired correctly and functioning properly. You can test the sensors individually using basic examples from their respective libraries.
🔚 Conclusion
This project demonstrates the power of integrating IoT sensors with cloud platforms to create a real-time monitoring system. With a simple setup, you can track temperature, humidity, and distance data and visualize it on a dynamic Ubidots dashboard. It's perfect for applications in environmental monitoring, smart homes, weather stations, and industrial IoT.

By utilizing MQTT, you can ensure efficient and real-time communication between the device and cloud, making this system scalable and lightweight.
