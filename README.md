# Camball – Flight Computer

> **Note:** Prototype description, some features not fully tested. Software will be developed after first PCB order.

**Version:** V1

## Summary

A flight computer (FC) with all features needed for standalone flight of a drone. Designed for small and light drone control with 4 brushed-DC motors each drawing up to 4 amps peak. Includes a feedback-loop for stabilization, implementing an IMU, magnetometer and motor current draw reference. The whole FC system is controlled by the STM32G491RET6 with exposed SPI for external controllers.

### Further features:

- Serial-Wire-Debug
- SPI interface for external controller
- Full battery management system (fast charging, some security features)
- Uses a voltage divider for battery voltage monitoring
- USB-C charging, power and data
- RGB LED indicator
- Exposed pads for reset/boot pins
- Motor drivers are wired for one-direction motor drive, no reverse motors.

![System Block Diagram](/images/diagram.png)

## Components

| Component | Name | Purpose | Notes | LCSC # |
|---|---|---|---|---|
| Controller | STM32G491RET6 | Main controller | Does sensor fusion and motor control, controlled by SPI | C3231005 |
| Sensor | BMI088 | IMU | Accelerometer and gyroscope. Data over SPI | C194919 |
| Sensor | TLV493DA1B6HTSA2 | Compass | Magnetometer. Data over I2C | C126688 |
| Voltage Regulator | TPS63031DSKR | Buck-boost to 3.3V | 1.8-5.5V input, 800mA supply | C15516 |
| Motor Driver | DRV8213DSGR | Control Motors | Has current sense built in, also many safety features | C22407186 |
| Battery IC | BQ24074RGTR | Battery charger | Switches power between USB and battery | C54313 |
| Battery | Spektrum | Power for Drone | 3.7V 800mAh 1S 30C LiPo | Amazon |
| Motor | 8520 coreless motor | Motor | ~5g | Amazon |
