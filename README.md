# Turn_Indicator
Bicycle turn indicator, build using Arduino, RGB-LEDs, 3D Printing and some elbow grease.

## Usage
[LEFT] [OFF] [RIGHT]
short press direction for 10s -> ring blinks
long press for unlimited -> ring on

short press OFF to turn off
long press OFF to turn on stand lights -> ring on

TODO add pictures


## Design choices

idempotent inputs instead of toggles, resists bouncing and is easier to understand

## Power

Full power down? 
- disconnect battery (possible?) 
- disconnect after board: easy, check standby usage
- deep sleep chip and LED off
- deep sleep chip and LED disconnect via MOSFET

APA idle: 1mA per LED
rings: 3mA per (3mm) LED on
Nano board: 30mA when on and working
- 12 mA when sleeping
-> test pro micro with desoldered power LED! should be 0.1mA

18650 boost board: 
0.0mA with switch open
0.8mA without load, probably power led

Conclusion: Disconnect at board, use whatever code and HW you want. 
