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