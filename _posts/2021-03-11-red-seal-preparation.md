---
layout: post
title: Red seal preparation
categories:
  -
---

# Fuel system

- Combustion knock - longer ignition delay period
    - cause by
        - low ambient temp
        - early injection timing
        - low injection pressure
        - fuel quality
    - fix by
        - block heater
        - glow plugs, manifold heaters
        - fuel heaters
        - retard timing for starting only
        - raise injection pressure for starting only
- white smoke - unburned fuel
    - cause by
        - lack of heat
        - low injection pressure
        - coolant burned
        - retard injection
- black smoke - not enough oxygen
    - lack of air: clogged air filter, defective turbo, leaking in intake components 
    - too much fuel, nozzle dribble
- blue smoke - oil is burned
    - worn piston rings
    - excessive crankcase pressure
    - leaking turbo
- primary filter
    - >= 25 microns
    - first filter after tank
    - combined with water separator
    - subject to vacuum
- secondary filter
    - >= 5 microns
    - on outlet side of transfer pump
    - subject to positive pressure
- final stage filter
    - >= 1 micron
    - just before injection pump
- filter service
    - close shut off valve if any
    - drain fuel from filter if any
    - turn filter on until gasket touch the base, then turn 3/4 turn
    - bleed the fuel system
        - use a priming pump until feel resistance on the plunger
        - crack return line on injection pump housing
- filter problems
    - loss power or stall if fuel filter clogged
    - loss power of seal is leak, broken, etc.
    - air in filter reducing volume of fuel injected, delaying injection timing, running rough
- transfer pump, self regulated, pulsating output, driven by cam and spring
    - diaphragm
    - plunger type
- pressure test fuel system
    - vacuum gauge installed on inlet transfer pump (inches of Hg, or mm of Hg) 1" of Hg = 25.4 mm of Hg
        - if # is higher the specs, prob can be
            - plugged pickup tub
            - plugged tank vent
            - clogged filter before transfer pump
    - pressure gauge on outlet of transfer pump or after secondary filter (1psi = 6.89 kPa)
        - if pressure is low
            - inlet restriction
            - worn pump
            - plugged filter
            - relief valve stuck in the open position
        - compare pressure before and after secondary filter to check pressure differential
    - flow test or pressure on the return line
        - higher pressure, less flow if return line is restricted
    - crank 30 second, cool for 2 minutes
- aerated fuel
    - submerge the return line watch for bubble while running engine >1000rpm
    - sight glass can be used to check for bubbles
- hot fuel cause loss of power 
    - as above 37.8C, every 5.5C increase, engine power decrease by 1%
- transfer pump problem
    - fuel coming from vent hole: diaphragm leaking
    - pressure low, leaking inlet, outlet valves
    - wear of plunger and bore
- relief valve 
    - stuck open, broken spring, low spring tension -> low fuel pressure
    - stuck close -> high pressure
    - sticking relief valve -> fluctuating
- injection pump
    - port and helix
        - barrel: intake port and spill port allow high pressure fuel exit at the end of injection 
        - plunger: has helix - a groove machined outside of plunger, determine effective stroke
        - advance timing by using intake turbo pressure to moving the fuel control rack which changing the effective stroke
    - opposed plunger
        - use adjustable cam ring
        - charging fuel from governer metering valve
        - displace high pressure fuel to injector when opposed plunger roll on cam lobes
        - advance timing by using transfer pump pressure to move the cam ring
    - install injector pumps
        - set 1st cylinder at TDC of compression
        - set injector pump at 1st cyl TDC of compression 
        - find TDC by using marks on housing or drop pin
- injector: nozzle holder, spring, nozzle returning nut, intermediate plate, nozzle assemble (need valve + nozzle body)
    - mutil-holes: used on direct injection engines - 2500~5000psi
    - pencil nozzle body and nozzle valve are a one assembly - 2500~4000psi
    - pintle (1 port): used indirect injection engines - 1400~2500psi
- injector problems
    - dirty fuel damage sealing surface bw needle valve & nozzle body, cause nozzle bribble which creating black smoke and nozzle tip coking
        - sticking needle valve resulting in misfire
    - overheat nozzle can brake down diesel creating nozzle tip coking, altering spray pattern
    - water in fuel cause corrosion, create higher pressure and enlarge injector holes
        - heat expand water particle can blow off tip
- injection pump governor
    - control low (base idle or curb idle) & high speed (no load)
    - allow operator input
    - sense rpm and metering fuel
    - supply enough fuel for startup or under heavy load

# Electronic system
- CAN 2.0 (Control Area Network) SAE J1939 250 kbps
- MID (Message Indentifier)

## sensors

- Thermistors
    - PTC: positive temp coefficient, temp increase, resistance increase
    - NTC: negative temp coefficient, temp increase, resistance decrease
    - wired in service with ECM: 1 lead is 5V ref, other is ground
- Pressure sensor
    - 3 wire: 1 ref, 1 ground, bridge voltage wire to ecm
- TPS: potentionmeter
    - 3 wire, 1 ref, 1 ground, signal wire to ecm

## SAE fault code 
- FMI: failure mode id - type of failure - 2 digits
- SID: system id - the operating system affected, (TPS, pressure sensor, etc.) - 3 digits
- PID: parameter id - engine oil pressure, coolant temp, etc. - 3 digits
- pressure sensor - high voltage
    - ref wire can be shorted to signal wire back to ecm, thus high voltage code
- temp sensor - low voltage
    - ref wire can be shorted to ground, thus 0V is seen bw ref and ground wire
- temp sensor - high voltage
    - ref wire to the sensor is broken, thus 5V is seen bw ref and ground wire
- Data link connectors:
    - 6 pin : J1587, J1708
    - 9 pin: J1939
    - key switch to be OFF when connecting data link port

# Electronically controlled fuel injection systems

## EUI - electronic unit injection

- components
    - cartridge valve control fuel flow into and out of injector
    - plunger push down create high pressure fuel
- fuel transfer system
    - around 65psi
    - supply clean cool, de-aerated fuel
- operations 
    - camshaft lift rocker arm, pushing the top of injector which pushing plunger, creating enough pressure to lift
    - stages
        - pre-injection
            - sol de-energized
            - poppet valve is opened
            - plunger push fuel return to tank
        - injection 
            - sol energized
            - poppet valve is closed
            - nozzle is opened
            - plunger continue to push down, injecting fuel to cylinders
        - spill
            - sol de-energized
            - poppet valve is opened, causing pressure drop, needle close immediately
            - plunger continue to push down, force fuel back to tank
        - fill
            - sol de-energized
            - poppet valve is opened
            - plunger moves upwards, suck fuel in, ready for next cycle        
- install new injectors required program new calibration code (e-trim) to ecm (every injectors may have fuel delivery variations because of mass production)

## HEUI - hydraulic electronic unit injection

- fuel transfer system
    - around 65psi
    - supply clean cool, de-aerated fuel
- operations
    - don't use camshaft, thus more responsive
    - pressurized engine oil act on intersifier piston which forcing fuel out of injector at high pressure
    - ecm monitor pressurized engine oil 870psi to 3500psi by IAP valve and sensor
    - stages:
        - pre-injection
            - sol's de-energized
            - poppet valve's closed
            - piston and plunger is stationary
            - nozzle's close
        - pilot injection
            - sol's energized 
            - poppet valve's opened let actuation pressure in
            - piston move down because of actuation pressure
            - 4500psi to open the nozzle
            - plunger has a groove, connected to the end of the plunger, when groove aligns with the spill port in the barrel, pressure drops, end pilot injection
        - main injection 
            - plunger keep move downwards cover spill port, nozzle's opened again to inject more fuel
        - end of injection
            - sol's de-energized
            - poppet valve closes, open the drain port on the top of poppet valve, allowing actuation oil pressure to escape
            - piston and plunger move upwards by return spring as actuation pressure's relief; this unseat the check ball, fuel suck into fuel chamber
            - nozzle closes, as fuel pressure drop
- IAP (injection actuation pressure ) valves determines pressure by using sensor inputs
    - throttle position - TPS
    - engine speed - VSS
    - manifold pressure - TBS
    - coolant temp - CTS
    - low actuation pressure is for low engine speed and light load
    - high actuation pressure is for higher engine speeds and loads

## Common rail fuel injection system
- components
    - common fuel rail (accumulator)
    - pressure limiting valve (relief valve), mounted at the end of the rail 
    - rail pressure control valve (similar IAP valve)
    - rail pressure sensor
    - flow limiting valves, used to prevent overfuelling of a cylinder in the event of an injector stuck in open position
        - it will shut off fuel flow to injector when it exceeds 1.5 times of the normal flow
    - injectors
        - needle valve is held by spring and fuel pressure on the top of intermediate valve
        - energize sol, bleed high pressure fuel off the top of the intermediate valve, which allow fuel pressure in the nozzle overcome spring pressure and inject
- fuel transfer system
    - around 80psi - 130psi
    - supply clean cool, de-aerated fuel

## Electronic unit pump (EUP) Mack, Mercedes

- components
    - electronic unit pump, camshaft actuated, 
- fuel transfer system
    - around 70psi
    - supply clean cool, de-aerated fuel
- stages:
    - fill
    - pre-injection
    - injection
    - spill
- install new injectors required program new calibration code (e-trim) to ecm (every injectors may have fuel delivery variations because of mass production)

## Service fuel system

- before taking injectors out do:
    - disconnect battery cable
    - use compress air at a regulated 65psi blowing to inlet fuel passage in cylinder head 
        - this is important, fuel trap in cylinder head can cause hydraulic lock, damage cylinder rod

## EGR - exhaust gas recirculation

- Introduce EGR into combustion chamber reduce NOx, but:
    - increasing CO and HC emissions
    - loss of power
    - reduced fuel economy
- EGR valve: butterfly or poppet
- EGR actuatior
    - air
    - electrical (PWM on motor)
- EGR cooler
    - air density decrease when it's hot, EGR cooler bring hot air down to 200C
    - cool by coolant, which require high-cap water pump
- ECM uses a differential pressure sensor to determine how much the EGR valve needs to open
    - 2 ports: 1 install at the inlet, one at the restriction (venturi)
- EGR temperature sensor is located in the delivery pipe before the mixer
- VDT variable displacement turbocharger or VGT variable geometry turbocharger
    - has vanes which can be closed to increase exhaust backpressure, which push more gas through EGR valve
- ECM control VDT under 3 modes:
    - EGR mode: 
        - EGR valve opens
        - adjusting position of vanes can increase exhaust backpressure and EGR flow
    - Brake mode:
        - EGR valve close
        - VDT's vanes is closed, which increase turbo boost, resulting in effective engine brake as more energy is need to push the piston up on the compression stroke
    - Boost mode (engine acceleration)
        - EGR valve close
        - ECM adjust vanes to provide correct boost

## After treatment

- combustion produce: CO, NOx, particulate matter, SOx
- DOC - diesel oxidation catalyst - reduce HC and CO emission
    - mounted as close as possible to engine to take advantage of the heat for catalyst
    - contains ceramic core coated with platinum or palladium as catalyst (help reaction happen at lower temperature)
    - core has diamond-shaped cell, arrange as honeycomb
    - CH + O2 = H20 + CO2; CO + 02 = CO2
- PDF is a regeneration soot (carbon) collector - reduce NOx and C
    - reduce soot
    - can be a simple filter, but it will clog fast not good for continuous operation
    - DPF can regenerate (self-clean) so extend service interval
    - core has diamond-shaped cell, arrange as honeycomb
    - NO2 + C (soot) = CO2 + NO
- regeneration
    - passive: exhaust temp > 500F, automatic
    - active: control by a switch, require vehicle park, cooling fan will be on, engine rpm increase
        - diesel is injected into exhaust downstream of turbo, diesel will be react with catalyst in DOC, thus increase temp ~ 1100F
        - inject by
            - dosing valve
            - pulsing engine's fuel injectors on exhaust stroke (common rails)
    - ECM monitor by 
        - 3 temperature sensor (plus before DOC)
            - control regen duration
            - warning light for high exhaust system temperature (HEST) on 450C & travel at 8 km/h
        - 2 pressure sensors (before and after DPF)
            - pressure drop increase will initiate regen and provide warning signal
- DPF cleaning
    - hazardous
    - DPF core is direction, so mark before removing
    - after cleaning, it has to be test for an accepted flow rate
    - thermal cleaning can be used as last attempt to restore DPF

- EGR system: use with DOC, DPF
- NO EGR system: DOC, DPF, SCR (selective catalyst reduction)
- SCR - selective catalyst reduction - use to reduce NOx just like EGR, but not lose power 
    - located down stream of DOC & DPF
    - DEF (diesel exhaust fluid) dosing pump, urea injector
    - exhaust temp sensor (inlet and outlet of SCR)
    - NOx sensor at outlet
    - NO + NO2 + 2NH3 = 3H20 + 2N2

# Notes

- DD Series 60: EUI
- DD 15, DD 16, common rail infection system

