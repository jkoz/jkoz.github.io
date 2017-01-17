---
layout: post
title: prepare ihet period 3
categories:
  -
---

# hydraulic principle

- work is force acting through a distance
- power is the amount of work done in a specific time 
$$ power={flow rate (l/min)  * pressure (Mpa) * 0.000583 \over efficiency} $$
$$ power={flow rate (gal/min)  * pressure (psi) * 0.0167 \over efficiency} $$
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
    - pressure compensated pump varies its displacement in response to system pressure
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
- if cavitation occurs on rod side, (pitch hole on rod), air and contamination could be pulled into the cyl past the rod seal and wiper

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

# hydraulic valves

## pressure control valves

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
    - allow full flow return to res and maintain minimum pressure at pump outlet 
    - work with a check valve
    - pilot sense from downstream of check valve (high pressure side)
    - pilot operated to handle full flow
    - closed center hyd sys with fix dis pump
    ![unloader](https://www.dropbox.com/s/a5oa6c36ezaqfv4/IMG_20161221_122612.jpg?raw=1)
    - demand type hyd sys with tandem fix dis pump (hi-low configuration)
        - normally closed, provide more flow with light load
        - when the load is high, the valve opens first pump's oil to tank, as we don't need too much flow
    ![tandem demand type](https://www.dropbox.com/s/z7heyww3qmnrrmw/IMG_20161221_113931.jpg?raw=1)
- pressure reducing valves
    - allow a circuit to have a max operating pressure that is less than the max system pressure
    - normally open
    - sense downstream of the valve
    - pilot operated to handle large flow rates
    - externally drain
    - **drain line** allows internal leakage return to the res preventing an internal hyd lock that would hold the valve in the open position
    ![prv](https://www.dropbox.com/s/wz06yfk3bfb6zk7/IMG_20161221_113943.jpg?raw=1)
- sequence valves
    - cause action occur in order
    - normally closed
    - sense upstream of the valve
    - externally drain
    - either direct acting or pilot operated
    ![sv](https://www.dropbox.com/s/t73s90xlwdemdxw/IMG_20161221_113955.jpg?raw=1)
- backpressure valves: counterbalanced, brake valves, and lock valves
    - control actuator movement by restricting return oil from the actuator
    - counterbalance valves
        - control safely lowering the load 
        - normally closed
        - sense upstream of the valve
        - internally drain
        - set maximum pressure on the vale match intended load to prevent cavitation rod end. 
        - work well with constant load
        - pressure intensification can happen if a restriction is put to return line of the rod end
        ![cbv](https://www.dropbox.com/s/wrf3darotkhamiv/IMG_20161221_114007.jpg?raw=1)
    - brake valves 
        - prevent the load from overspeeding the motor and modulate deceleration no matter what the lad
        - 2 sense lines counteract spring force
            - first senses upstream of the actuator, acting on large piston surface
            - second senses upstream of the valve or downstream of the actuator, acting on small piston surface
            - support cushion the load when suddenly changing to neutral, prevent shock load by using second pressure
        - internally drain
        ![bkv](https://www.dropbox.com/s/6kkhwxapodo6sof/IMG_20161221_114040.jpg?raw=1)
    - lock valves or pilot operated check valves (basically, a safety valve)
        - hold load when hyd line rupture, prevent overspeeding, and drifting due to leakage
        - used in blade lift circuit of graders to avoid cyl drift during operation
        - used in outriggers to avoid crane roll over if there's leakage
        ![lckv](https://www.dropbox.com/s/35vjyfzbx8l97k6/IMG_20161221_114105.jpg?raw=1)

## accumulator

- weight (constant regardless of vol oil), spring, gas (piston, bladder)
- purpose:
    - store engergy
    - shock absorption
    - gradual pressure build up (applications like handling fragile load, e.i. eggs)
    - constant pressure maintenance: absorb oil when pressure rise and deliver oil when it falls

## flow control valves

- actuator speeds depends on its capacity and flow rates
- non-pressure compensated flow control use a variable orifice to feather the oil flow
    - adv : work best with constant pressure
    - dis : speed of actuators varies as the load changes
- pressure compensated flow control maintain constant oil flow by maintaining constant pressure drop across orifice
![pcfcv](https://www.dropbox.com/s/oand03902wkjz3y/IMG_20161221_145723.jpg?raw=1)
- bypass type flow control
    - used with fixed displacement pump
    - excess flow can be wasted
![btfc](https://www.dropbox.com/s/wkayg9vqmk1m3rj/IMG_20161221_150026.jpg?raw=1)
- restrict type flow control
    - used with pressure comp pump
    - normally open valves
    - closed when experience high pressure, send signal to destroke pump.
    ![rtfca](https://www.dropbox.com/s/h5h2slrqrc5oe84/IMG_20161223_140721.jpg?raw=1)
    ![rtfc](https://www.dropbox.com/s/nc622xtobwhpn09/IMG_20161221_151741.jpg?raw=1)
    - meter in
        - load pulling the actuators may cause cavitation
        - control the speed of cyl extension
        - work best if the load oppose the cyl movement
        ![mi](https://www.dropbox.com/s/ws6wivxzbygc4ys/IMG_20161221_153012.jpg?raw=1)
    - meter out
        - work well despite the load changes and directions
        - overruning load can cause pressure intensification
        ![mo](https://www.dropbox.com/s/sc16u7akgmopnkf/IMG_20161221_153027.jpg?raw=1)
- flow dividers
    - priority flow dividers
        - divert all flow to a primary circuit (steering) before flow to implement circuit
        - normally closed implement circuit
        ![pfd](https://www.dropbox.com/s/iko5e5a73o7l539/IMG_20161221_154619.jpg?raw=1)
        ![pfda](https://www.dropbox.com/s/qguycbxybzg8crm/IMG_20161221_154659.jpg?raw=1)
    - proportional flow dividers
        - ensure the same amount of oil flow passes through each of outlet ports regardless of pressure variations
        - load on outlet 1, restrict on outlet 2; thus reducing flow on outlet 2
    ![pfda](https://www.dropbox.com/s/zvsdgdfg7uhjzi9/IMG_20161221_155205.jpg?raw=1)

## directional control valves

- poppet valve: check valve
- rotary spool valves
    - higher internal leakage
    - used in low pressures and flow rate application, like controlling pilot oil flow
- slide spool valves
    - handle high pressures and flow rate with minimum leakage
    - the goose trap oil for better lub and sealing, allowing pressurized oil to act around the spool, centering, preventing binding, and excessive wear
    - notches help metering oil flow
    - diverter valves : 2 positions dcv
    - float mode : work ports connect to tank (loader boom, grade blade lift) usually use detent to hold in float position 
- center types
    - open center dcv
        - work with system relief
        - fixed displacement pump
        - open center, closed port
        - open center, open port (motor or float center)
            - use with 2 brakes valve on working lines to prevent shock load and drift
    - closed center dcv
        - fixed displacement with unloader valves
        - pressure comp var dis pump
- dcv actuators
    - mech actuation (lever, foot pedal, push button)
    - pilot operated (hyd or air)
        - reduce effort to move dcv
        - remote actuation
        - sliding pool type pilot dcv: does not regulate pressure applied on main dcv
        - pressure regulating controller: provide accurate dcv movement by regulating pilot pressure to the dcv
    - electrical (selenoid)
        - electric-over-pilot : easy & economical remote control with greater pilot force 
- dcv detenting
    - mech
    - electromagnetic can work with proximity switch on loader to stop the boom movement
- dcv accessories
    - system and circuit relief
    - load check valves: prevent a suspended load from momentarily dropping when dcv is moved from hold to raise
    - anti cavitation valves:
        - prevent a void forming in the actuator when the load overrun the pump
        - located between work port and return passage in the dcv
        ![atcv](https://www.dropbox.com/s/451nbbaa66ic9y8/IMG_20161223_141717.jpg?raw=1)

    - **flow compensator** 
        - provide accurate flow (speed) to the actuators regardless of the load
        - ensure constant pressure drop across the dcv spool by sensing pressure before and after dcv spool
        - use double check valves on working lines to assist compensator spring regardless of the dcv position
            - ensure that the highest load pressure is sent to the compensator
        ![compv](https://www.dropbox.com/s/mjk74qs1xjdy0p0/IMG_20161222_162739.jpg?raw=1)
- multi dcvs
    - unibody: compact, less point for external leakage, hard to maintenance
    - valve stacks
- multi dcv conns
    - open center dcv conns
        - series passageway
            - have a passage through the valves to the res
            - priority given to the first pump
            ![spss](https://www.dropbox.com/s/plz9365aacfuvgv/IMG_20161222_170515.jpg?raw=1)
        - tandem center conn
            - return oil back to passageway
            - actuators move together as both dcvs are actuated
            ![tdcn](https://www.dropbox.com/s/x08ovuu6g0q6jw2/IMG_20161222_170520.jpg?raw=1)
        - series-parallel conn
            - oil flow to series passageway in neutral
            - oil flow to operators drawn from the para passageway
            - actuators move together, the lightest load actuator will have priority
            ![spcnn](https://www.dropbox.com/s/3vymu3m0dzbok7q/IMG_20161222_175119.jpg?raw=1)
    - closed center dcv conns
        - don't have a series passageway
        - valves connected para, including aux
        ![ccdccn](https://www.dropbox.com/s/db8d725g3vs5d00/IMG_20161222_175639.jpg?raw=1)
- methods to connect an auxiliary dcv to open center hyd sys
    - diverter valve
    - power beyond sleeve
    - flow divider

# hydraulic system types 

## open center (constant flow sys)

### fix dis pump and load check valves

- cheap (repair and purchase)
- used of load check valves
- used for low percentage of machine's duty cycle, such as haul truck hoist circuit, wheel loader
- always have flow in the series passageway allowing oil return to tank in neutral

### constant horsepower open center (used pressure comp pump)

- regulate pump flow based on pump output pressure, excavator
- low pressure -> upstroke to get high displacement
- high pressure -> destroke to get low displacement (to limit max power drawn from engine)
- designed to operate engine at a constant speed
- used side-by-side pressure comp pump
- upstroke and destroke based on
    - power shift pressure generated by PRV (power shift proportional reducing valve) 
        - based on selected speed
        - PRV pressure decrease, pump output increases
    - negative flow control (NFC) from main control valve GP (group)
        - NFC pressure decrease, pump output increases
    - cross sensing signal pressure from out put of the two pumps
        - cross sensing pressure decrease, pump output increases

## close center

- fix dis pump with accumulator and unloader valve
    - similar to **"open center with fix dis pump & load check valves"**
    - there's constant oil flow in neutral
- demand flow system or pressure comp hyd sys
    - used pressure comp pump
    - flow is provided when it's required for work
- load sensing hyd sys
    - provide precise amount of flow and pressure to perform work demanded by actuators
    - minimum waste energy
    - actuator speed will not change as the load changes
    - keep the pump outlet pressure slightly higher than the load pressure, margin pressure (150 - 450psi)
    - load sense spool or flow comp or margin spool
        - control flow (affect actuator speed)
        - margin pressure: 350 psi
    - pressure limiting spool or pressure comp or cutoff spool
        - control pressure (2900 psi)
    - dozer
    - stages
        - engine off
            - flow comp dump oil in the control piston
            - max wash plate angle
        - stand by
            - pump outlet pressure force flow comp destroke control piston reduce wash plate angle
            - minimum wash plate angle
            - produce just enough oil to make up for leakage
            - stand by pressure is slight higher than margin pressure to overcome flow comp's spring to activate the control piston
        - upstroke
            - load pressure signal stops "flow comp" keeping the control piston pressure 
            - oil in the control piston is dumped to tank
            - bias spring wins
            - max wash plate or pump upstroke 
        - constant flow
            - pressure drop across dcv is stable (dcv is fixed at a position)
            - flow comp's spring pressure + load pressure = pump output pressure
            - the contained oil in the control piston will be pump at fixed rate
        - destroke
            - load pressure drops
            - pump output pressure wins
            - flow comp open passage for oil going to the control piston
            - pump is destroked
        - high pressure stall
            - stall actuators
            - pump is upstroking to handle the load
            - flow comp's spring pressure + load pressure is less than pump output pressure
            - flow comp blocked oil going to the control piston => max wash plate angle
            - pressure comp notice that max pressure is reached 2900psi
            - pressure comp allows oil going to the control piston => dewash the pump
            - pressure comp overrides flow comp to destroke the pump
    - adjust flow comp and pressure comp springs
        - fcs weaken : result low flow rate.at any load and dcv position
        - pcs weaken: result machine weaker, function normally at light load, but can not create higher work pressure
        - fcs tension increase
            - at higher load, pump overdraw engine power, thus stall it
        - pcs tension increase
            - machine can be stronger than before because it is gonna create more pressure
            - but power demand could exceed the supply

## hydrostatic transmission

![hst](https://www.dropbox.com/s/pirsviqqgjrgrd3/IMG_20161229_132325.jpg?raw=1)

- the most common setup: closed circuit with var dis, rev pump
- open loop circuit: returning oil from actuator go to tank (loader)
    - res interrupt path of oil
    - good for dissipate heat
- closed loop circuit/HST: oil return to pump inlet
- can have var dis pump or motor
- infinite rpm
- load can not overrun the motor
- charge pump
    - deliver oil to either side of closed loop circuit
    - deliver oil to dcv control the pump direction and displacement
    - provide cool oil to closed loop circuit
    - make up internal leakage
    - prevent cavitation for main pump 
    - supply oil for aux attachment like hoist or lift circuit
- flushing valve
    - draw cooler oil from output side supplying to motor
    - orifice on the valve will regulates the amount of oil used to flush the motor 
    - the flushing relief valve ensures that minimum pressure is maintained on the low side of closed circuit, this protect HST pump from cavitation

## hyd systems service

- gather information
    - service manuals, bulletins, operator manuals
- talk to operators
    - what job were you doing with the machine when the problem occurred?
    - when was the machine last serviced?
    - have any repairs or modifications been done to the machine recently?
    - have the problem been evident for a long time or did it just appear suddenly?
    - did you notice anything unusual, noises or erratic movements before the machine failed?
- visual inspection
    - check oil level, correct oil?
    - check oil filter, check quantity and type of contamination trapped 
    - oil condition (foamy, milky, dirty)
    - oil leaks?
    - overheating (burnt paint, blue color)
    - check damage (dent cyl barrel, bent, scored cyl rods, collapse hose, crushed tubing) 
- operational test
    - check fluid level first!
    - should be safe to operate
    - steps
        - warm up hyd oil by stalling actuator @ wide open throttle (150-180F)
        - operate
            - response slow, jerky?
            - unusual smell, noises? 
            - smoke?
            - @ what point, problem occurs
        - measure actuator speed (flow issue)
            - to determine if there are excessive flow losses (too much leakage) 
            - check cycle times
            - take 3 or 4 measurement and get avg 
            - check motor rpm (both direction)
        - perform stall test (pressure issue)
            - result depends on what type of hyd sys used
            - to check engine rpm when hyd sys is @ max load
            - used tachometer when a actuator is stalled @ W.O.T
            - engine rpm drop excessively
                - engine lacks of power
                - relief valve is set to high
                - misadjust unloader valve or pump comp 
            - engine rpm drop slightly
                - engine power has increased
                - relief valve is set to low
- pressure testing
    - pressure gauge
        - snubbers are orifices placed in the gauge inlet to dampen pressure pikes, protecting the gauge components
        - range should be twice the expected pressure
    - tee test
        - gauge installed in para with the tested area 
        - shut-off valve is protect the gauge, open when measuring pressure
        - need to open to put the tee; thus, contamination can enter
        - builtin pressure taps need to be cleaned before installing gauge
    - common location for installing pressure gauge
        - close center
            - before the pump
                - low pressure (cavitation on outlet)
                    - inlet restricted
                    - driveshaft speed too high
                    - wrong oil used
                - high pressure (air in system, cause jerky operation)
                    - inlet leaking, air drawn to system 
            - after the pump
                - neutral pressure @ W.O.T
                    - filter, fitting,return line
                    - localize hotpots
                - working pressure (NO load)
                    - resistance dcv, fitting, actuators, linkages, etc.
                - working pressure (max load or pressure) 
                    - stalling actuators @ W.O.T
                    - pressure too high => adjusting system relief
        - closed center load sensing
            - check for pilot pressure on dcv or bw double check valves
        - HST
            - closed circuit pressure: 
                - one read charge pressure
                - one read working pressure
                - check max closed circuit pressure by stalling motors @ W.O.T
            - charge pressure
                - insufficient pressure cause cavitation
            - case drain pressure
                - pressure's too high causing pump or motor damage
- flow testing
    - slow cycle time
    - check of hotpots, e.i. cylinder barrel
    - small leakage: check cyl drift by using a tape to make the rod 
    - check cyl seal leaks
        - fully extend cyl
        - remove the rod end hose 
        - raise (extend) cyl @ W.O.T
        - measure oil from removed return line in "10 seconds"
    - check motor internal leakage
        - drain line secure to test container
        - stall motor @ W.O.T
        - measure oil from drain line in "10 seconds"
    - hydraulic test unit
        - including flow meter, pressure, temp, and load control
        - pressure gauge should be installed upstream of load control 
        - always backoff load control before test
        - series conn: test pump efficiency
            - 2 types of connections: bypass & inline conn
            - flow rate @ no load is slower than specs 
                - restricted inlet
                - aeration
            - flow rate @ full load (increase load control to the pressure specified by manufacture)
            - efficiency less than 80%, pump should be serviced 
        - tee test: test circuit leakage
            - perform this test after confirm pump efficiency
            - can used to check system relief
                - there is wide pressure difference bw cracking and full flow pressure, the relief valve is broken
            - adjust load control slightly below cracking pressure of system relief valve
            - **compare this flow rate with flow rate @ full load during pump testing**
            - circuit leakage = pump full load flow - circuit flow
# electrohydraulics

- clamping diode
    - dissipate current flow created by induce voltage upon energize, protect relay contact
- proportional solenoid
    - varying current causes varying valve spool movement
    - use PWM to reduce the heat generated by large voltage drop
- electronic control system types
    - open loop
        - there's no feedback signal to the ECU indicating the extent of output action
    - closed loop
        - include sensors that send feedback signal to ECU 
        - provide more accurate control of its position, velocity, or acceleration
        - servo valves can be used (wheeled vehicle steering system) 
- electronic control module (ECM) or programmable logic controller (PCL)
- duty cycle is a percentage of on time compared to off time
- proximity switches are commonly used in loader bucket and lift height control systems.
- when deflector plate is in close proximity to the switch, the switch is closed
- the loader bucket kickout position and lift height can be adjusted by adjusting the position of the proximity switch in relation to the deflector plate
- switch sends a discreet voltage signal
- the force created by a proportional solenoid is proportional to output voltage signal from ECU
- using dither to keep the spool moving or vibrating sightly, stiction (or hysteresis) is prevented

# misc

- close center hyd system often called demand flow
- axial displacement pump
    - the center line is para with the pump drive shaft
- water glycol fluid contain 40% of water and 60% of glycol (more glycol)
- water/oil emulsion contains 60% of water and 40% oil (more water)
- invert emulsion contains 40% of water and 60% of oil (more oil)
- most multiple pump conf use a common inlet
- with control valves connections are often referred as ways
- cam radial piston motors, the cam surface is ground with ramps space 90 degree apart
- flood lamps on a machine is controlled by the key switch control circuit
- thrust pin on differential carrier helps prevent movement of differential carrier during different loads
- thrust crew prevents the bevel gear deflecting during high load applications
- metallic components can use steam cleaning or Varsol
- bearing/friction disc clean with Varsol (mineral spirit)
- carrier internal components clean with petroleum products 
- accumulator suspension is set too high cause driveline problems
- bronze coloured particles in filters means clutch failure
- powershift trans : cycling applications e.i dozer, loader(fixed stator)
- automatic trans : hauling applications e.i scrapers (freewheeling stator)
- circuit breakers
    - type 1:
        - law for headlights 
        - **auto reset** to keep light on
        - typically **gold**
    - type 2:
        - has heater (resistor)
        - once tripped will not reset until **load removed** or **power discontinued**
        - used for all circuits other than headlamps
        - typically silver in **color**
        - there's wire connect 2 terminal, current run though this wire to keep bimetall warm, not to auto reset
        - if we have short-to-ground, it draw more current. as long as fix the short, current drawn drops
    - type III
        - manual reset
        - look exactly like type II with a button on top to reset the breaker
- battery disconnect switch prevent the discharge of the battery group when equipment is parked
- safety power control circuit - flood / working lamp
- flywheel checks
    - crankshaft end play
    - flywheel housing bore eccentricity (base on fw)
    - flywheel housing face squareness (base on fw)
    - crankshaft hub eccentricity (base on housing)
    - crankshaft hub face squareness (base on housing)
---------
1 cm = 0.394 inches
1 m = 39.37 inches
1 micron = 1 / 1 million meter = 
1 psi = 6.89kPa
1 bar = 100kPa


