---
layout: post
title: prepare ihet period 3
categories:
  -
---

# hydraulic principle

- work is force acting through a distance
- power is the amount of work done in a specific time 
- power = {flow rate (l/min)  * pressure (Mpa) * 0.000583 \over efficiency}
- metric const: 0.0167
- potential : pressure
- kinetic : flow rate (velocity)
- in pipe : potential + kinetic = constant
- cylinder: flow rate = cyl vol / time
- 1 gal = 231 cubic inches
- power loss
    - pressure loss: potential energy is change to heat energy. small conductor, abrupt change cross session, direction
    - flow loss : slower hyd func, heat, too much clearance, wear
    - back pressure is the resistance to flow on the return side of comp
- series: same flow rate, split pressure: limit torque
- para: split flow rate, same pressure : more torque
- viscosity : resistance to flow
    - low: oil film thinner, improve flow characteristics
    - high: oil film thicker
    - need: adequate film strength for lub and able to flow to small clearance
- vi : ability resist changes in viscosity as temp changes (at least 90)
- ester base fluid
    - produce acid on exposing to water
    - react with zinc, brass, bronze
    - swell **nitrile-based** seal (Buna N)
    - **compatible with Viton (EPR) seals**
- replace filter after 100 hours to remove built-in contamination
- faulty air breathers draw dirt to reservoirs
- leaked pump inlet cause air and contamination entering system
- rod seal and wipers are wear ingress more contamination
- uncleaned maintenance schedule
- strainer in res at least 200 mesh
- catastrophic, intermittent, degradation failures

# pumps

- gear :  6 * W * (2D - L) * (L - D) / 2
- vane : 12 * W * {(L + D) / 4} * {(L - D) / 2}
    - inlet ports are paced 180 apart, same as outlet ports
    - vane pockets increase in vol in inlet, decrease vol outlet ports
    - the high point of bevelled tip is the leading edge in the rotation
    - oil passage is drilled from behind the vane (on bevelled face)
    - can have arrow on housing or on rotor
    - require to flip the rotor and vane if its is bevelled tip
- piston pump
    - pressure comp pump varies its displacement in response to system pressure
        - bias spring want full flow
        - stroking piston sense system pressure want zero displacement
- pump flow rate: pump displacement (cubic meter) * rpm
- pump efficiency: 
    - mechanical : friction
    - volumetric: inter nal leakage
    - overall = mech + vol
- cavitation
    - restricted inlet

# actuators

## cyl

- piston seal leaks
    - reduce cyl speed
    - cyl drift in the extension direction
    - pressure intensification when the load is applied on piston rod in the retraction direction
- piston relief allows oil bypassing the piston when the piston reaches the end of its stroke
    - used in mobile equipment that has limited res vol to prevent heat up the oil
- single acting cyl
    - ram type: guide ring support the inner end of the piston tube, but does not seal the piston in the barrel
- cyl cushion
    - slow down cyl rod when it reaches the end of its stroke
    - prevent shock load when piston come to its end
    - restrict oil when the piston reach its end stroke
- cyl return drill
    - allow oil is returning though small drilling in the cyl barrel when the piston end its stroke.
    - control deceleration of cyl movement
- quick drop valves
    - quick drop or extend the piston by pumping oil from rod end to base end
    - power down: when the blade hits the ground, stop pumping oil from rod end to base end, thus, providing max down force
    - normal drop by feather dcv, (not regenerate)
- apply light coating of hydraulic oil to the seals and surfaces they must slide over to make installation easy, and prevent seal stretch or damage
- after installing cyl, check and adjust system relief (especially if the old cyl was failed because of excessive pressure)

# motor

- speed depends on flow rate and motor displacement
- torque depends on inlet pressure and motor displacement which influence the surface area
- gear motor: poor torque
- gerotor or orbit motor : high torque & low rpm (1 revolution of shaft, all lobes must be exposed to pressurized oil)
    - the spool valve directs the flow of oil to and from the valleys in the rotor element
- case drain allows some internal leakage (lub and cool parts) returning to res
- piston pump:
    - larger swash plate angle, motor displacement increases => torque increase, speed decrease
    - smaller swash plate angle, motor displacement decreases => torque decrease, speed increase
    - pressure compensated motor varies its displacement in response to changes in the load
    - bias spring try to keep minimum swash plate angle => max speed, min torque
    - comp spool sense inlet pressure want maximum swash plate => max torque, min speed
- **motor will hydraulically lock and stall in the zero displacement position**
- disassemble
    - housing should be marked
    - external gear pump is non-hunting, should be marked
    - pistons should be kept in in their original bores (cylinder barrel)
- overloading
    - excessive pressure
    - crack housing
- contamination
    - sandblasted
    - heavy core
    - inspect filter, strainers
- cavitation
    - pitted erosion
    - the load overrun the motors, motor rotates faster than the pump supplies; inlet pressure falls too low
- lack of lub
    - heavy wear
    - blue color
    - improper oil

# hydraulic valve

- pressure control valves
    - direct acting : ball, poppet, guide poppet
        - high amount of override pressure, causing waste power, generates unwanted heat
        - used low flow rate applications or infrequent duty cycles
    - double acting
        - less override pressure required
        - pilot valve has big spring deal with high pressure, low flow rate
        - other valve has ligh spring deal with low pressure, high flow rate
        - less prone to chatter
        - operate through a wider pressure range
    - applications
        - pressure relief
            - system relief: limit system pressure
                - double acting
                - pass full flow rate as little pressure override
                - excessive override pressure cause relief valve to crack well within operating pressure range
                - adjust @ high idle
                - hold maximum pressure; max load on the pump, max energy converted to heat
            - circuit relief : limit pressure in one branch or circuit, protect comp from pressure pike (shock load)
                    - does not require to handle full flow
                    - adjust @ low idle to avoid valve override cause inaccurate reading
                    - can use hand pump to adjust
    - unloader valves
        - work with a check valve
        - pilot sense from downstream of check valve (high pressure side)
        - closed center hyd sys with fix dis pump
        - demand type hyd sys with tandem fix dis pump 
        ![tandem demand type](https://www.dropbox.com/s/z7heyww3qmnrrmw/IMG_20161221_113931.jpg?raw=1)
- accumulator
    - weight (constant regardless of vol oil), spring, gas (piston, bladder)
    - purpose:
        - store engergy
        - shock absorption
        - gradual pressure build up (applications like handling fragile load, e.i. eggs)
        - constant pressure maintenance: absorb oil when pressure rise and deliver oil when it falls

- flow control valves
- directional control valves
