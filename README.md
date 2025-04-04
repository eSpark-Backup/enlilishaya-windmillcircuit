# Wind Mill Circuit Design and Development
#### Client Name: Enlil Ishaya

## Project Requirements
Design a circuit to power 10 LEDs using an alternator and a rechargeable battery. The circuit is driving its power source from a Wind Mill. Additionally, the circuit will incorporate motion detection (to detect movement of wind mill), a timer relay, and a wireless remote control. There is a current solution that is built off of aftermarket breakout parts but it has one major problem. **The circuit when powered via alternator does not charge battery and neither powers LEDs properly. When on battery, everything works fine.** Below is a detailed breakdown of the requirements:

### Functionality:
- Primary Power Source - Alternator:
    - The alternator generates AC power (1V/50 RPM, up to 12V AC max) and should:
        - Power the 10 LEDs when running **(TBD)**. This is optional due to stability issues.
        - Charge a 3.7V 9900mAh Li-Ion rechargeable battery using a charging module. TP4056 is suggested but open to better options.
- Battery Backup:
   - When the alternator stops, the battery should automatically power the LEDs without interruption.
   - Prevent the battery from powering the LEDs while it is being charged to avoid damage **(TBD)**.
Motion and Timer Control:
- A magnetic reed switch to detect motion. **If better option is available, it can be added in place of Reed Switch**
    - If no motion is detected, a 10 - minute timer relay will start, shutting off the LEDs after 10 minutes of inactivity.
- Wireless Remote Control:
    - A 433 MHz RF remote control switch should allow manual control of the LEDs.
    - If the LEDs are turned off via the remote, they should remain off even if motion is detected.
    - If the LEDs are turned on via the remote, the 10-minute timer should engage when no motion is detected.
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
- Wireless RF Remote Control:
    - 433 MHz RF switch to toggle LEDs on/off manually, overriding timer and motion sensor.
- LEDs:
    - 10 LEDs with current-limiting resistors.
    - Exact LED info **TBD**
### Key Requirements:
- Automatic Power Switching **(TBD)**:
    - Seamlessly switch between alternator and battery power without interruption.
- Power Management and Battery Protection:
    - Prevent simultaneous battery charging and discharging to protect the battery.
- Integrated Controls:
    - Ensure proper interaction between the motion detector, timer relay, and RF remote control for desired functionality.
- Protection and Safety:
    - Include circuit protection (e.g., fuses or diodes) to safeguard components.
