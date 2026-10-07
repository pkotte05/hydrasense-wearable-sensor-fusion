# HydraSense

Wearable sensor fusion platform for physiological state estimation, focused on early detection of dehydration-related changes.

**Status:** active prototype. HydraSense is an engineering research platform, not a medical device, and it has not been clinically validated.

## Overview

HydraSense is a wrist-worn embedded device that combines several low-cost physiological and environmental signals into one estimate instead of relying on a single sensor. It reads skin conductance, skin temperature, heart rate, and ambient temperature and humidity, and uses them to compute a Hydration Risk Index with color-coded alert levels. The project began as a competition-driven medical innovation concept and has grown into a platform for studying embedded sensor fusion and wearable biosensing.

## Why sensor fusion

Hydration is hard to read from one signal. Heart rate changes with exertion and stress, skin conductance shifts with temperature and movement, and ambient heat and humidity change how both should be interpreted. Reading the signals together, with environmental context, is the core idea of the project.

## Hardware

| Component | Role |
|---|---|
| ESP32 | Control, data handling, and interface logic |
| GSR skin conductance sensor | Electrodermal activity |
| DS18B20 waterproof temperature sensor | Body-adjacent skin temperature |
| SHT31 | Ambient temperature and humidity |
| MAX30102 | Optical heart rate (photoplethysmography) |
| OLED display | On-device readout |
| Joystick-style controller | Non-touch navigation |
| Vibration motor | Optional alerts |
| LiPo battery with TP4056 USB-C charging module | Power and charging |

## User interface

A non-touch interface built around an OLED display and a compact joystick, chosen for reliability, low power draw, and use where touch is inconvenient. It has six tabs: Home, GSR, Temperature, Ambient, Heart Rate, and Settings.

## Development progress

- 3 complete hardware iterations to improve integration and stability
- 2 dedicated test rigs for troubleshooting and signal inspection
- 4 enclosure revisions designed in SolidWorks for wrist-worn packaging
- 20+ validation-focused bench tests covering sensor behavior, fit, layout, and system response
- A multi-tab embedded interface for practical navigation

## Roadmap

1. Consolidate the prototype: a stable sensor set, cleaner wiring and layout, and reliable power and charging.
2. Collect structured data under controlled conditions: resting baseline, post-activity, recovery, and varied ambient conditions.
3. Analyze the data: preprocessing, feature extraction, and simple classification logic.
4. Test whether fused signals are more informative than any single signal, and document noise sources and limits.
5. Longer term: a custom PCB, a companion app, and classical machine learning models such as random forests.

## Limitations

- No validation results are published yet. The index and its alert levels are not claims of clinical accuracy.
- GSR and heart rate are affected by movement, stress, and temperature. These confounders are what the planned validation is meant to quantify.

## Repository status

This repository currently contains documentation only. Firmware, enclosure CAD, and test data are planned additions.
