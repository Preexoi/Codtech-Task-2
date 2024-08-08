Name: Preethi T
Domain: Embedded System
Duration: July to August 2024
Company: Codtech IT Solutions Pvt. Ltd
ID: CT08DS6334

Temperature and Humidity Monitoring with DHT22 - TinkerCAD Simulation

This project simulates temperature and humidity monitoring using an Arduino and a DHT22 sensor in TinkerCAD. The sensor provides real-time data on temperature in both Celsius and Fahrenheit and humidity levels as a percentage

Project Overview

Objective:
Monitor the ambient temperature and humidity using the DHT22 sensor and display the results in the Serial Monitor.

Components Used:
- Arduino Uno
- DHT22 Sensor
- 10kΩ Resistor (for DHT22 data line)
- Breadboard
- Jumper wires

Software:
- TinkerCAD

 Circuit Diagram

- DHT22 Pinout:
  - VCC to 5V on Arduino
  - DATA to digital pin 2 on Arduino
  - GND to Ground (GND) on Arduino
  - 10kΩ resistor between DATA and VCC

Code Overview

cpp
#include "DHT.h"

#define DHTPIN 2      // Pin connected to the DHT22 sensor
#define DHTTYPE DHT22 // DHT22 (AM2302) sensor type

DHT dht(DHTPIN, DHTTYPE);

void setup() {
  Serial.begin(9600);
  dht.begin();
}

void loop() {
  delay(2000);  // Wait a few seconds between measurements
  
  // Reading temperature and humidity from the sensor
  float humidity = dht.readHumidity();
  float tempC = dht.readTemperature();
  float tempF = dht.readTemperature(true);

  // Check if any reads failed and exit early (to try again)
  if (isnan(humidity) || isnan(tempC) || isnan(tempF)) {
    Serial.println("Failed to read from DHT sensor!");
    return;
  }

  // Print the results to the Serial Monitor
  Serial.print("Humidity: ");
  Serial.print(humidity);
  Serial.print(" %\t");
  Serial.print("Temperature: ");
  Serial.print(tempC);
  Serial.print(" °C ");
  Serial.print(tempF);
  Serial.println(" °F");
}


How it Works

1. Setup Phase: The setup() function initializes the Serial Monitor and starts the DHT22 sensor.

2. Loop Phase: The loop() function runs repeatedly, reading the temperature (in Celsius and Fahrenheit) and humidity from the DHT22 sensor every two seconds. The data is then printed to the Serial Monitor.

 Running the Simulation

1. Open TinkerCAD: Navigate to TinkerCAD and open the Arduino simulation environment.
2. Build the Circuit: Use the DHT22 sensor and connect it to the Arduino as per the circuit diagram.
3. Upload the Code: Copy and paste the provided code into the TinkerCAD code editor.
4. Start the Simulation: Run the simulation to see the temperature and humidity data in the Serial Monitor.

 Conclusion

This project introduces you to monitoring environmental conditions using a DHT22 sensor and an Arduino. This basic setup can be expanded to log data over time or trigger actions based on specific temperature or humidity levels.

