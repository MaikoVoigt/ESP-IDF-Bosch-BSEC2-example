idf_component_register(
    SRCS "main.cpp"
    INCLUDE_DIRS "."
    REQUIRES I2Cbus BSEC2 BME68x esp_timer driver freertos esp_system
)