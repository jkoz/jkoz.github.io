---
layout: post
title: electrical ihe
categories:
  -
---

# truck electrical accessory circuits

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

