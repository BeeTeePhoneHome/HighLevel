High Level File Notes
=====================
Description of Each File
---------------------
- Common: defines namespace common for checksum and namespace elcano for Origin and Waypoint classes and Curve, Location_mm, and Junction structs
- Globals: list of defines for namespace elcano
- High_Level.ino: makes Localization and Pilot objects called myLocal and myPilot and calls their respective update functions in the loop passing Waypoint objects as parameters
- Kalman: implements Kalman filter logic
- KF_IO_PC: used in Kalman filter
- Localization: used for the vehicle to determine its current location
- Matrix: used in Kalman filter
- Pilot: instantiates Planner object and contains tests for past destination, approaching/leaving intersection, getting the turn direction angle, finding the state, initializing position, populating path, and a check for proper heading
- Planner: contains AStar struct and path planning/finding/building
- Settings_HighLevel: defines ORIGIN_LAT, ORIGIN_LONG, MAX_CAN_FRAME_DATA_LEN_16, MAX_WAYPOINTS, TURN_RADIUS_MM, MIN_TURNING_RADIUS_MM, TURN_SPEED, DESIRED_SPEED_mmPs

Current Functionality
---------------------
(TBD)



Libraries Needed from Adafruit
---------------------
Links to Addition Libaries NEEDED from Adafruit! 
Download the following ZIP files. In the Arduino IDE, go to "Sketch > Include Library > Add .ZIP Library" and select the downloaded ZIP file.

1. Adafruit_GPS -> https://github.com/adafruit/Adafruit_GPS
2. Adafruit_Sensor -> https://github.com/adafruit/Adafruit_Sensor
3. Adafruit_L3GD20 (Triple Axis Gyroscope) -> https://github.com/adafruit/Adafruit_L3GD20
4. Adafruit_LSM303 (Accelerometer + Magnetometer) -> https://github.com/adafruit/Adafruit_LSM303DLHC
5. due_can library https://www.arduinolibraries.info/libraries/due_can

Notes:
* I2C must modify "Wire" to "Wire1" in the cpp file use SCL1 and SDA1 (with pullup resistor) for Arduino Due  
* In above LSM303.cpp file, change ALL occurrences of Wire to Wire1 except for the initial include of <Wire.h>. This is needed for the Magnetometer to work.
* In the Arduino IDE, do not select the "Arduino Duemilanove or Diecimila" board under tools. You may need to go to board manager, search "Due", and install the "Arduino SAM Boards (32-bits ARM Cortex-M3)" board. That will give you a separate "Arduino ARM (32-bits) Boards" section under boards, from which you can select either the Arduino Due (Programming Port) or Arduino Due (Native USB Port).