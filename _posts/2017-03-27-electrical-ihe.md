---
layout: post
title: On Road Electrical
categories:
  -
---

# truck electrical accessory (fundamentals)

| hydraulic                                   | electrical                         |
|---------------------------------------------+------------------------------------|
| pump                                        | battery                            |
| flow                                        | amperage (current)                 |
| - pump create flow                          | - load draw amp                    |
| pressure                                    | voltage                            |
| - load - resistance to flow create pressure | - load - battery (source) create vol |

Mack:
- red: straight from battery (not protected with fuse)
- black: ground
- white: protected
- 2.0 metric wire size
- wire: 36-A-2.0
    - fuse 36
    - first component in circuit
    - 2.0mm wire size

- American Wire Gauge (AWG)
    - smallest wire: 18 gauge - 0.8mm
    - *16 gauge - 1.0mm^2* (area of cross section)
    - *14 gauge - 2.0mm^2*
    - *12 gauge - 3.0mm^2*
    - 10 gauge - 5.0mm^2
    - 8 gauge - 8.0mm^2

- pull in go through the motor
- hold in go to battery
- relay
    - 30 power in
    - 87a (NC), 87 (NO) out to the load
    - 85, 86 (ground) pull in wiring
- fuse
    - type 1: (gold) once stay strip, will constantly reset (head light) (no heater)
    - type 2: (silver) has resistor (heater) inside to keep bimetal from reset
    - type 3: manual reset with button
- NTC: negative temp coefficient
    - excess current, resistance decrease
- PTC: positive temp coefficient
    - circuit protector devices
    - excess current, resistance increase
- electrical is drawn in non energized position
- switches
    - SPST: single pole, single throw, ON-OFF
        - poles: sets of terminals
        - throws: positions
        - the pin in the middle is voltage in 
        - the pins in top or bottom are voltage out
    - SPDT: single pole, double throws, ON-ON or ON-OFF-ON
        - control 1 circuit the same time although we have 2 separated circuits
    - DPST: double poles, single throw
        - control two separated circuit at the same time
    - DPDT: double poles double throws
- tractor/truck: signal override brake
- trailer: brake and signal are separated
- acid core solder has an internal acid flux that will react with cooper wire to cause corrosion and increased resistance, use rosin core solder
- silver the best conductor
- power line use aluminum with steel core
- the solenoid's magnetic field collapses when the voltage is removed, the collapsed voltage creates an induced voltage (self-induction) causing arcing at the switch
- clearance/marker & tail light 
    - control by master lighting switch
    - clearance/marker light - armber, yellow, upper region of the truck outline
    - tail light - red - rear dimension
- fiber optic dash illumination
    - used light source to illuminate
- dc motor speed increase, CEMF (counter electromotive force) increases
    - high starting torque because of lack of CEMF at the begining
- two types of dc motors
    - permanent magnet dc motor
    - field wound dc motors
- parallel wound dc motor (shunt motor)
    - field coils parallel with armature wiring
    - CEMF generated by armature does not effect the flow of current through the field coil
    - stable speed, low starting torque 
    - fan blower motor
- control speed of dc motors
    - variable electrical resistance
    - multiple shunt windings
    - PWD
- commercial motor vehicle safety association (CMVSA)
- battery isolation switches prevents batteries from discharging while the truck is parked
    - fused has to be added to protect constant power accessories
        - crack engine with the switches is open, or to have bad ground
- install parallel-connected capacitor to reduce static noise 
- vehicle tracking system
    - satelite tracking system, (global positioning system, GPS)
    - communication component (digital satelite uplink)
- truck data monitoring
- tire pressure control system
    - based on road contact surface
        - less pressure - large - more traction & heat
    - vale pack box recieve control signal to add or discharge air from rear wheels
- truck position sensing
    - collision warning system (CWS) (front-end, turn off @ 15mph)
    - adaptive cruise control (ACC)
    - collision mitigating system (CMS) (rear-end, turn off @ 15mph) 
- meritor wabco abs
    - electronic stability control (ESC)
    - roll stability control (RSC)
    - automatic traction control (ATC)
- windshield wiper control system
    - the park contacts supply current to the motor after the wiper is turned off, allowing the motor to continue operating until the wipers reach the park position (@ lower moulding edge of the windshield)
- gauges and sending units
    - direct acting gauges
        - speedometer (road speed) - transmision output shaft speed
        - tachometer (engine rpm) - fuel pump or camshaft speed
    - indirect acting gauges
- starting circuit
![starting](https://www.dropbox.com/s/fqte0qenu2z2dbx/IMG_20160401_092752.jpg?raw=1)
