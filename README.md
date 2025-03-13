# BSEC2 Library for ESP-IDF

This repository demonstrates how to use the Bosch BSEC2 library with the ESP-IDF framework directly without PlatformIO. It shows a working example for the ESP32-S3 board.

## Project Overview

This project provides a native ESP-IDF implementation for the Bosch BME68x sensor using the BSEC2 library. It adapts the example originally developed by [luar123](https://github.com/luar123/Bosch-BSEC2-Library/blob/master/examples/generic_examples/basic_idf/src/main.cpp) for PlatformIO to work directly with ESP-IDF's build system.

## Repository Structure

The project is organized as an ESP-IDF project with the following components:

- **BSEC2**: Bosch's Sensor Environmental Cluster library for air quality sensing
- **BME68x**: Driver library for the BME68x sensor
- **I2Cbus**: Communication library for ESP32 I2C interface

## Used Libraries and Sources

This project makes use of the following libraries:

- **BSEC2 Library**: Fork by [luar123](https://github.com/luar123/Bosch-BSEC2-Library) of the original [Bosch BSEC2 Library](https://github.com/boschsensortec/Bosch-BSEC2-Library)
- **BME68x Library**: Fork by [luar123](https://github.com/luar123/Bosch-BME68x-Library) of the original [Bosch BME68x Library](https://github.com/boschsensortec/Bosch-BME68x-Library)
- **I2Cbus Library**: [esp32-I2Cbus](https://github.com/natanaeljr/esp32-I2Cbus) by natanaeljr

These libraries have been integrated as components within the ESP-IDF project structure.

## Usage for Different ESP32 Boards

This example is configured for the ESP32-S3 by default. To use it with other ESP32 boards:

1. Modify the BSEC2 library's `CMakeLists.txt` file to link the appropriate precompiled library for your specific board
2. Refer to [this CMakeLists.txt](https://github.com/MaikoVoigt/Bosch-BSEC2-Library/blob/master/CMakeLists.txt) for an example of how to adjust the file

For example, to use with ESP32 (not S3), change:
```cmake
target_link_libraries(${COMPONENT_LIB} INTERFACE "${CMAKE_CURRENT_SOURCE_DIR}/src/esp32s3/libalgobsec.a")
```
to:
```cmake
target_link_libraries(${COMPONENT_LIB} INTERFACE "${CMAKE_CURRENT_SOURCE_DIR}/src/esp32/libalgobsec.a")
```

## Cloning the Project

### Clone the Repository with Submodules

```bash
# Clone the repository
git https://github.com/MaikoVoigt/ESP-IDF-Bosch-BSEC2-example

# Change to the project directory
cd ESP-IDF-Bosch-BSEC2-example

# Initialize and update all submodules
git submodule update --init --recursive
```

This step is essential to download all required libraries as they are included as Git submodules.

## Notes

- This project demonstrates a native ESP-IDF implementation without relying on PlatformIO
- The original examples were adapted to use the ESP-IDF build system directly
- The BSEC2 library requires a specific precompiled library file for each ESP32 variant

## Credits

- Original libraries by [Bosch Sensortec](https://github.com/boschsensortec)
- PlatformIO adaptation by [luar123](https://github.com/luar123)

## License

Please refer to the respective libraries for license information.

