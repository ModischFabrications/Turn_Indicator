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

Using idempotent inputs instead of toggles, resists bouncing and is easier to understand. 

## CAD

Zipties for handlebar mounts and indicators? 

Using screws is nice if you have a clear mating surface and thick walls. A cage-style-basket or the handlebar has neither of those. 
Therefore you need either a coupling plate or, as done in my case, cheap and flexible zipties. They can adapt to a wide variety of widths and forms while being cheap and readily available. 

The handlebar mount is just a extra to increase grip and can be done as one half or both. bake sure to prevent rotation when pressing by padding with a silicone/rubber sheet underneath. Screwing in or out of the mounting plate is irrelevant, in this case the screw is just easier to access from the clamp. 

Contact surfaces for covers for the enclosures are slanted to decrease the chance of water creeping in. 

The cutout of the LEDs is beveled by design to prevent a hard cutoff of the light cone, this bevel should feather the borders a bit. 


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

Conclusion: Power is disconnect on the boost board, so you can use whatever code and HW you want. 
