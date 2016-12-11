---
layout: post
title: powershift and automatic transmission
categories:
  -
---

# fundamentals

## gear ratio 

The number of revolutions the input (drive) gear makes to complete one revolution of the output (driven) gear.

## gear reduction

- small gear drives bigger gear
- input **speed decrease**, torque increase by gear ratio

## override

- big gear drives smaller gear
- input speed increase, torque decrease by gear ratio

## Single planetary gear set operational combinations

| speed                              | input   | output   | held       |
| :--------------------------------- | ------- | :------- | :--------- |
| first speed reduction (greatest)   | sun     | pc       | ring       |
| second speed reduction             | ring    | pc       | sun        |
| first speed override (mildest)     | p.c     | ring     | sun        |
| second speed override              | p.c     | sun      | ring       |
| first speed reverse (underdrive)   | sun     | ring     | p.c        |
| second speed reverse (override)    | ring    | sun      | p.c        |

- **neutral**: no input or no held member
- **direct drive**: locking 2 members or driving 2 members at the same speed

## Allision transmission

- clutch application chart
- rotating: C1, C2
- stationary: C3, C4, C5

| ranges/clutches   | C1    | C2    | C3    | C4    | C5    |
| :---------------: | :---: | :---: | :---: | :---: | :---: |
| reverse           |       |       | x     |       | x     |
| neutral           |       |       |       |       | x     |
| first             | x     |       |       |       | x     |
| second            | x     |       |       | x     |       |
| third             | x     |       | x     |       |       |
| fourth            | x     | x     |       |       |       |
| fifth             |       | x     | x     |       |       |
| sixth             |       | x     |       | x     |       |

## powershift transmission:

- operator control the ranges, we put in first, then it's always run at first gear, etc.
- upshift (4speed) to protect engine even if operator put it in first (insanely)

## powershift control system

### control circuit

1. after pump may have priority flow control which redirect oil to brake and steering first (then send oil to trans after satisfying that first), such as dozer (or we must have other pump for that)
2. shift selector valve (valve body, basically a dcv) 
3. for example we are in neutral, c5 locked up, oil will be sending to clutch pressure regulator valve (pressure increase to 400psi, then regulator valve open)
4. oil will be feed to tc relief valve (control maximum system pressure, just like system relief)
5. oil send out from tc go to filter and cooler then back to lub circuit (don't need to be a high pressure circuit) (which lub trans)

### pump

a. trans scavenaging pump: 
b. tc scavenaging pump: get rid of oil in tc housing to prevent pressure build up
c. charging trans pump
d. steering clutch pump

- modulation is an action controlling how fast the clutch applied which means control speed or flow (to avoid shock load on gear, and wear of clutches)
- modulator is a component
- modulation relief valve: control maximum trans pressure in dcv
- ratio valve: limit maximum pressure in torque converter (depend on viscosity of the oil will determine how the valve move)
- clutches spring relief, oil applied (don't need to be safety, not brake)
- leakage on seal of clutch piston cause slow application of piston

### electronic shift control system

- speed sensor: (AC)
    - slow speed: low voltage, low frequency
    - fast speed: high voltage, high frequency
- throttle position sensor:
    - no throttle: high voltage
    - wide open throttle (WOT): low voltage
- solenoid: used PWM signal
    - proportioning

- abs light on, => don't go to lockup => burn transmission 
- too much clutches clearance will affect application

### hydraulic shift control system

- positions: applied, released, and hold
- governor from road speed
    - low speed: low pressure (oil)
    - high speed: high pressure
- modulator pressure from throttle
    - low throttle: high pressure
    - high throttle (wot): low pressure
- control above factors, we have ability to control shift at different time
- impeller has pump but it supply oil for torque converter
- governor gets oil from shift circuit
- clutch application pressure: 400psi, full flow, full pressure
    - low throttle, keep orifice closed (figure 27)
    - high throttle, orifice wide open (we don't want slippage)
    - orifice can be control by throttle linkage or vacuum line from engine intake manifold
- first and second are always the hard shift

# service

- fix the cause of the problem, not the result
- question to ask before service: why it fails, what's going on 
- subscription for manual services: www.prodemand.com, alldata, ondemand
- typical troubleshooting steps
    1. gather information, check oil level
        - for transmission, check oil level while engine is running, say in neutral
    2. talk to operator
    3. visual inspection: check filter (can be the first step)
    4. operation tests
        - try to simulate problem
        - ask the operator to reproduce problem if he's there
        - do stall test, to separate trans and tc problem
            - check operating temp (transmission 150-180F)
            - apply brake, lower blade/implements
            - highest gear possible
                - most load on transmission
                - least load on drive train
            - engine @ w.o.t - max 30 seconds | engine @ w.o.t in neutral to cool torque converter
            - measure engine rpm 
                - low speed (mostly tc problems): low engine power, slipping stator, (oil goes wrong angle, causing resistance)
                - high speed (mostly trans problem): slipping clutch (try different gears if a gear cause high speed, probably we have slipping clutches on that gear)
        - look at binding linkages
        - listen noise, smell
        - pressure and flow test
            - pressure test first cause' it's easy to put in on test ports; use double expected pressure gauges
            - high vacuum at suction line, we may have orifice at suction line, we will have cavitation pump
            - lockup, main, lub, C1-5 taps for pressure gauges
        - turn shift signal valve 1-2 notch with shift point adjustment tool to adjust how agressive we shift
