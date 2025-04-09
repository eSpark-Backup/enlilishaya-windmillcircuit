# Wind Mill Circuit Design and Development
#### Client Name: Enlil Ishaya

## Project Requirements
Design a circuit to power 10 LEDs using an alternator and a rechargeable battery. The circuit is driving its power source from a Wind Mill. Additionally, the circuit will incorporate motion detection (to detect movement of wind mill), a timer relay, and a wireless (BLE) control. There is a current solution that is built off of aftermarket breakout parts but it has one major problem. **The circuit when powered via alternator does not charge battery and neither powers LEDs properly. When on battery, everything works fine.** Below is a detailed breakdown of the requirements:

### Functionality:
- Primary Power Source - Alternator:
    - The alternator generates AC power (1V/50 RPM, up to 12V AC max) and should:
        - Power the 10 LEDs when running. This is optional due to stability issues.
        - Charge a 3.7V 9900mAh Li-Ion rechargeable battery using a charging module. TP4056 is suggested but open to better options.
- Battery Backup:
   - When the alternator stops, the battery should automatically power the LEDs without interruption.
   - Prevent the battery from powering the LEDs while it is being charged to avoid damage.
Microcontroller Unit:
- An MCU for BLE processing and logical control on the board.
Motion and Timer Control:
- A magnetic reed switch to detect motion. **If better option is available, it can be added in place of Reed Switch**
    - If no motion is detected, a 10 - minute timer relay will start, shutting off the LEDs after 10 minutes of inactivity.
- BLE based Mobile Application Control:
    - If the LEDs are turned off via the BLE, they should remain off even if motion is detected.
    - If the LEDs are turned on via the BLE, the 10-minute timer should engage when no motion is detected.
- State Retention:
    - The circuit must retain the last state of the LEDs (on or off) regardless of motion detection.
### Components:
- Alternator:
    - Model: B00224 (1V/50 RPM, max 12V AC, 4-wire output)
- Step-Down Buck Converter:
    - LM2596HV (Adjust input AC voltage to suitable levels for TP4056 and LEDs)
- Charging Module:
    - TP4056 (Handles Li-Ion battery charging with overcharge protection)
- Battery:
    - 3.7V 9900mAh Li-Ion rechargeable battery (18650 type)
- Timer Control Relay:
    - Controls LED shutdown after 10 minutes of inactivity.
- Motion Detector:
    - Magnetic reed switch to detect motion and reset the timer.
- BLE Based control:
    - A BLE based mechanism to control via a mobile application, similar functionality needed as was being fulfilled through RF in v1.0 of design.
    - Preferred solution to have chip antenna for better range.
- LEDs:
    - 10 LEDs with current-limiting resistors.
    - Exact LED info **TBD**
### Key Requirements:
- Automatic Power Switching:
    - Seamlessly switch between alternator and battery power without interruption.
- Power Management and Battery Protection:
    - Prevent simultaneous battery charging and discharging to protect the battery.
- Integrated Controls:
    - Ensure proper interaction between the motion detector, timer relay, and BLE control for desired functionality.
- Protection and Safety:
    - Include circuit protection (e.g., fuses or diodes) to safeguard components.
- Intellingence on-board:
    - An MCU based design to perform processing of BLE and other related logics.

### PCB Dimensions and Requirements
Some key notes:
- The terminal blocks to be placed on right and left edges (similar to v1.0 of design) but moved inwards by 0.5cm.
- Three or Four standard mounting holes required in the design on the edges.
- Battery should be placed on the PCB. Preferred location below the alternator cutout area. Placement should be proper and through a battery holder if possible for user convenience.
- Rough dimensions below:
![image](https://github.com/user-attachments/assets/109b2ca4-86d2-4442-8f19-66942dc18803)
