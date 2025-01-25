<p align="center">
<img src="https://github.com/ProDesLab/NiCE5340_V1.0-SoM/blob/main/Media/NiCE5340%20header%20logo%20w.jpg" width="500">
</p>
<p align="center">
<img src="https://github.com/ProDesLab/NiCE5340_V1.0-SoM/blob/main/Media/1714388781094.jpg" width="400">
</p>
<p align="center">
<img src="https://github.com/ProDesLab/NiCE5340_V1.0-SoM/blob/main/Media/NiCE5340%20Block%20Diagram.jpg" width="400">
</p>

I had been wondering for some time what would be the result of combining a powerful low-power MCU with a versatile low-power FPGA. <br />
I could not find anything around that satisfied me, so I decided to make it myself. <br />
Curiosity drove me to design something as small as possible with as many devices on board as possible. <br />
The type of components used falls into the category for developing low-power IoT applications or wearable devices. <br />
So it is with pride that I present a small SoM with an MCU from Nordic Semiconductor at its center: nRF5340. <br />
Accompanying it is a little gem from Lattice Semiconductor, the well-known: iCE40 Ultra Plus <br />
Needing to choose a name for this project, I thought of combining the two part numbers, and so  <br />
it is with real pleasure that I present it to you: 𝗡𝗶𝗖𝗘𝟱𝟯𝟰𝟬 <br />
Really “nice” isn't it ? <br />

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
 - Discharge Current Measurement - **INA231AIYFDT** (Texas)
 - RTC - **MAX31342EWA+T** (Analog)

As can be seen in the block diagram and schematic, all peripherals share the same I2C bus. <br />
An 'INA213' current meter has been placed at the battery input and allows the total system consumption or battery charging current to be measured. <br />
All peripheral devices connected to the 1V8 rail can be switched off completely by the MCU, which allows power consumption to be minimised. <br />
The FPGA package used does not have very many pins, but the two available banks have already been configured to run at 1V8 or 3V3 on the GPIO. <br />
A chip antenna and an **MHF4** connector for external connection were also integrated on the module. <br />
There is also on-board ESD protection for the USB bus. <br />

NOTE: <br />
I did this work to exercise deliberate practice, to improve my design skills and to push my miniaturisation skills further. <br />
(not really true, I have done more complicated in the past but I wasn't the one paying the bills) <br />
