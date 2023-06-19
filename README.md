# Arduino Bootloader Burning Guide

This repository contains various files gathered from different sources on the internet, compiled in one place to provide users with a convenient resource for burning bootloaders. It is important to note that **I do not claim ownership of these files** and give full credit to the original owners and contributors.

## Disclaimer

**Please exercise caution while using these files and follow the instructions carefully.** Burning a bootloader requires technical knowledge and can potentially damage your hardware if not done correctly. **You assume all responsibility** for any consequences resulting from using these files or following the instructions provided.

## Instructions

To burn a bootloader onto an Arduino using another Arduino as an ISP, follow these steps:

### Step 1: Preparing the Arduino ISP

1. Connect the working Arduino (ArduinoISP) to your computer via USB.
2. Open the Arduino IDE on your computer.
3. Select the correct board model and port corresponding to the working Arduino (ArduinoISP) under the **Tools** menu.
4. Upload the "ArduinoISP" sketch to the working Arduino (ArduinoISP) using the Arduino IDE. The sketch can be found under **File → Examples → ArduinoISP**.

### Step 2: Connecting the ATmega328PB Arduino

1. Connect the ATmega328PB Arduino that you want to burn the bootloader onto to your computer via USB.
2. Ensure that the ATmega328PB Arduino is connected to the Arduino ISP as follows:
   - Arduino ISP **RESET** to ATmega328PB **RESET**
   - Arduino ISP **MISO** to ATmega328PB **pin 16**
   - Arduino ISP **MOSI** to ATmega328PB **pin 15**
   - Arduino ISP **SCK** to ATmega328PB **pin 17**
   - Arduino ISP **5V** to ATmega328PB **VCC**
   - Arduino ISP **GND** to ATmega328PB **GND**

### Step 3: Selecting the Correct Board

1. In the Arduino IDE, click on the **Tools** menu and select **Board**.
2. Choose the appropriate ATmega328PB board variant based on the clock type you have:
   - **ATmega328PB (Crystal Oscillator)** if you have an external crystal connected to the ATmega328PB board.
   - **ATmega328PB (External Clock)** if you have an external clock source connected to the ATmega328PB board.
   - **ATmega328PB (Internal Clock)** if you're using the internal clock of the ATmega328PB board.

   Note: The selection depends on the specific configuration of your ATmega328PB board.

### Step 4: Adding the Board to the Boards Manager

1. Open the Arduino IDE and go to the **Preferences** menu (File → Preferences).
2. Look for the "Additional Boards Manager URLs" field and click on the button with the arrow icon on the right.
3. Add the following URL to the dialog box that appears: `https://github.com/watterott/ATmega328PB-Testing/raw/master/package_m328pb_index.json`
4. Click **OK** to close the dialog box.
5. Open the **Boards Manager** by going to the **Tools** menu and selecting **Board** → **Boards Manager**.
6. Search for "ATmega328PB" in the Boards Manager search bar.
7. Click on the entry named "ATmega328PB by MCUdude" and click the **Install** button.
8. Once installation is complete, close the Boards Manager.

### Step 5: Burning the Bootloader

1. Go to the **Tools** menu and select the appropriate settings for **Board**, **Processor**, and **Port**.
2. Select **Arduino as ISP** under **Tools → Programmer**.

   Note: Make sure you have selected the **Arduino as ISP** programmer. Do not select any other programmer option.

3. Click on the **Burn Bootloader** option under the **Tools** menu.
4. Wait for the bootloader burning process to complete.

   Note: During this process, the Arduino ISP will transfer the bootloader code to the ATmega328PB Arduino. It may take a few seconds, so please be patient.

5. Once the burning process is finished, you will see a message indicating successful bootloader burning.

Congratulations! You have successfully burned the bootloader onto your ATmega328PB Arduino using another Arduino as an ISP.

## Troubleshooting Steps

If you encounter any issues during the burning process, try the following troubleshooting steps:

1. Verify that all the connections between the Arduino ISP and ATmega328PB Arduino are correct and secure.
2. Ensure that the correct board variant is selected for the ATmega328PB Arduino, based on your clock configuration.
3. Double-check that the Arduino ISP is selected as the programmer in the Tools menu.
4. Check if the ATmega328PB board is properly recognized by your computer by verifying the port selection.
5. Try restarting the Arduino IDE and reconnecting the Arduino boards.
6. If you continue to face difficulties, refer to the documentation or support channels of the respective repositories for further assistance.

## Common Mistakes

Here are some common mistakes to avoid:

1. Connecting the Arduino ISP and ATmega328PB Arduino with incorrect pin mappings or orientations.
2. Selecting the wrong ATmega328PB board variant that doesn't match your clock configuration.
3. Choosing a different programmer option instead of "Arduino as ISP" in the Tools menu.
4. Neglecting to install the necessary board files using the Boards Manager.
5. Failing to establish a stable USB connection between the Arduino boards and your computer.

Please ensure that you follow the instructions carefully, double-check your connections, and consult the troubleshooting steps if needed.

## Credits

This repository includes files from the following sources:

- [Elektor Labs Arduino](https://github.com/ElektorLabs/Arduino)
- [Watterott ATmega328PB Testing](https://github.com/watterott/ATmega328PB-Testing)
- [Optiboot](https://github.com/Optiboot/optiboot)

Full credit for these files and their contributions goes to their respective owners and contributors. Please refer to the individual files for specific credits and licenses.

Note: The provided .zip file contains the necessary files for burning the bootloader onto the ATmega328PB Arduino.

