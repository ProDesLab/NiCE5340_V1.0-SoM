<p align="center">
<img src="https://github.com/ProDesLab/NiCE5340_V1.0-SoM/blob/main/Media/NiCE5340%20header%20logo%20w.jpg" width="500">
</p>
<p align="center">
<img src="https://github.com/ProDesLab/NiCE5340_V1.0-SoM/blob/main/Media/1714388781094.jpg" width="400">
</p>
<p align="center">
<img src="https://github.com/ProDesLab/NiCE5340_V1.0-SoM/blob/main/Media/NiCE5340%20Block%20Diagram.jpg" width="400">
</p>

## What is NiCE5340 ?
NiCE5340 SoM is the combination of the capabilities of two devices: a microcontroller and an FPGA. <br />
In this case, it is a Nordic **nRF5340** MCU and a Lattice **iCE40** FPGA. <br />
From the fusion of these two names comes the **NiCE5340**. <br />

The system can be powered by a single lithium cell, and the small but powerful **nPM1100**, also from Nordic, takes care of the charging. <br />
Supporting the system between the MCU and FPGA is a **64Mbit QSPI flash memory**, whose bus is also accessible from external pins. <br />
Various sensors, devices and peripherals have been integrated on board, such as:
 - 6DOF IMU - **LSM6DSMTR** (ST)
 - Biosignal Converting Unit - **AS7057-BWL** (Osram)
 - Magnetometer - **MMC3630KJ** (Memsic)
 - SAR Sensor (touch) - **SX9328ICSTRT** (Semtech)
 - PDM MEMS MIC - **ICS-41351** (TDK)
 - Humidity/Temperature - **SHTC3** (Sensirion)
 - Haptic Driver - **DRV2605LYZF** (Texas)
 - RGB IR Colour Sensor - **BH1749NUC-E2** (Rohm)
 - Barometric Pressure Sensor - **DPS310XTSA1** (Infineon)
 - Charge/Discharge Current Measurement - **INA231AIYFDT** (Texas)
 - RTC - **MAX31342EWA+T** (Analog)

As can be seen in the block diagram and schematic, all peripherals share the same I2C bus. <br />
An 'INA213' current meter has been placed at the battery input and allows the total system consumption or battery charging current to be measured. <br />
All peripheral devices connected to the 1V8 rail can be switched off completely by the MCU, which allows power consumption to be minimised. <br />
The FPGA package used does not have very many pins, but the two available banks have already been configured to run at 1V8 or 3V3 on the GPIO. <br />
A chip antenna and an **MHF4** connector for external connection were also integrated on the module. <br />
There is also on-board ESD protection for the USB bus. <br />
