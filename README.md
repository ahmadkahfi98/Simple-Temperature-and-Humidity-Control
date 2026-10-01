# Arduino Temperature & Humidity Monitoring System

## Project Overview

This project is a simple temperature and humidity monitoring system developed using an Arduino and a DHT22 sensor. The system continuously measures the environmental conditions of a room and activates an output device when the measured temperature or humidity reaches a predefined threshold.

The project was developed and tested using the **Wokwi simulation platform**. The buzzer is used as the output indicator in the current simulation, but the same output concept can be adapted to control other actuators, such as a fan, depending on the application requirements.

## Objectives

The main objectives of this project are:

* Measure room temperature using a DHT22 sensor.
* Measure room humidity using a DHT22 sensor.
* Process the sensor readings using an Arduino.
* Monitor the measured values continuously.
* Activate an output device when a predefined threshold is reached.
* Demonstrate a basic sensor-based control system using Arduino.

## Components

### Hardware

* Arduino Uno
* DHT22 Temperature & Humidity Sensor
* Buzzer
* Jumper wires

### Software

* Arduino IDE
* Wokwi Arduino Simulator

## System Architecture

The basic system architecture is:

```text
             DHT22 Sensor
            /            \
           ↓              ↓
    Temperature        Humidity
           \              /
            \            /
             ↓          ↓
              Arduino
                 │
                 ↓
          Threshold Check
                 │
                 ↓
          Output / Actuator
                 │
            ┌────┴────┐
            ↓         ↓
          Buzzer     Fan*
          
* The output can be adapted to control other actuators.
```

The DHT22 provides temperature and humidity measurements to the Arduino. The Arduino processes the measurements and compares them with the predefined threshold values.

When a threshold condition is reached, the Arduino activates the output device.

## System Operation

The system continuously reads temperature and humidity values from the DHT22 sensor.

The Arduino then compares the sensor readings with the defined threshold values.

The current control logic is:

```text
Read Temperature & Humidity
          │
          ↓
    Compare with
      Threshold
          │
          ↓
  Threshold Reached?
       /       \
     YES        NO
      │          │
      ↓          ↓
 Output ON    Output OFF
```

In the current simulation, the output is a buzzer.

For a practical implementation, the same control signal could be used to control an appropriate actuator, such as a fan, through a suitable driver circuit or relay module.

## Threshold Condition

The current simulation uses the following threshold conditions:

```text
Temperature ≥ 30 °C
OR
Humidity ≥ 30 %
```

When either the temperature or humidity reaches or exceeds its threshold, the buzzer is activated.

When both values remain below their respective thresholds, the buzzer remains off.

The threshold values can be modified in the Arduino code according to the requirements of the application.

## Simulation

This project was developed and tested using **Wokwi**, an online electronics simulation platform.

The simulation allows the Arduino and DHT22 sensor to be tested without physical hardware.

> **Note:** This repository contains a simulation-based prototype. The current implementation uses a buzzer as the output device.

## Expected Output

### Normal Condition

When the measured temperature and humidity are below their respective thresholds:

```text
Temperature: 28.5 °C
Humidity:    25 %
Buzzer:      OFF
Status:      NORMAL
```

### Warning Condition

When either temperature or humidity reaches or exceeds its threshold:

```text
Temperature: 30.2 °C
Humidity:    25 %
Buzzer:      ON
Status:      WARNING
```

or:

```text
Temperature: 28.5 °C
Humidity:    32 %
Buzzer:      ON
Status:      WARNING
```

## Potential Real-World Applications

The basic concept can potentially be developed for applications such as:

* Room environmental monitoring
* Equipment room monitoring
* Storage room monitoring
* Laboratory environmental monitoring
* Automated ventilation systems
* Temperature and humidity warning systems

For example, the buzzer in this simulation could be replaced by a fan control system. When the temperature exceeds the selected threshold, the Arduino could activate the fan through an appropriate driver circuit.

## Future Improvements

Possible improvements for future versions include:

* Replacing the buzzer with a fan or other suitable actuator.
* Adding an LCD or OLED display.
* Using an ESP32 for Wi-Fi connectivity.
* Adding real-time remote monitoring.
* Implementing data logging.
* Adding an IoT dashboard.
* Allowing temperature and humidity thresholds to be configured.
* Adding automatic ventilation control.
* Sending notifications when abnormal conditions are detected.

## Project Status

**Status:** Completed — Simulation Prototype

**Platform:** Wokwi

**Microcontroller:** Arduino Uno

**Sensor:** DHT22

**Output:** Buzzer

**Application:** Temperature and Humidity Monitoring
