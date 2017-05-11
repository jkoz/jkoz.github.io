---
layout: post
title: Powershift and Automatic Transmission
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

## planetary trans components

- turbine shaft
    - tc output
    - splines to rotating clutch module C1 friction discs, C2 clutch drum
- mainshaft
    - connect to C1 clutch drum
    - sun gear of P2, P3
- output shaft
    - driven by P3's pc

## Single planetary gear set operational combinations

- reduction: pc driven
- override: pc drive
- reverse: pc held
- **neutral**: no input or no held member
- **direct drive**: locking 2 members or driving 2 members at the same speed

| speed                              | input   | output   | held       |
| :--------------------------------- | ------- | :------- | :--------- |
| first speed reduction (greatest)   | sun     | pc       | ring       |
| second speed reduction             | ring    | pc       | sun        |
| first speed override (mildest)     | p.c     | ring     | sun        |
| second speed override              | p.c     | sun      | ring       |
| first speed reverse (underdrive)   | sun     | ring     | p.c        |
| second speed reverse (override)    | ring    | sun      | p.c        |

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

## powershift trans control system

### control circuit

- after pump may have priority flow control which redirect oil to brake and steering first, then send oil to **clutch application circuit** (400-500psi)
- shift selector valve (valve body, basically a dcv) makes transmission speed and direction changes 
- for example we are in neutral, c5 locked up, oil will be sending to clutch pressure regulator valve, pressure increase to 400psi, then clutch pressure regulator valve open, allow oil sent to **tc charging circuit**
- oil will also be feed to tc relief valve control maximum system pressure (50-125psi)to prevent damage to tc components.
- oil send out from tc go to filter and cooler then back to lub pressure relief valve before going to **the trans lub circuit** (don't need to be a high pressure circuit) (which lub trans)
    - lub pressure relief valve dump oil to transmission case if pressure is over 30 or 50psi
    - trans is pressure lub, don't need to be submerged in oil which cause overheating
    - prevent trans turning during towing: elevate drive wheels, remove drive axles, remove driveline
- **clutch pressure** regulator valve limit the application pressure applied to the transmission clutch piston 

### components

- pump groups
    - trans scavenaging pump: remove oil from trans housing prevent pressure buildup which causing overheat
    - tc scavenaging pump: get rid of oil in tc housing to prevent pressure build up
    - charging trans pump provides oil for clutch app circuit, tc charging circuit, & lub circuit
    - steering clutch pump provides oil for the steering clutch and brakes 
- **priority valve** ensure oil pressure is available for the steering clutch and brake circuit for the trans clutch app circuit (300psi).
- transmission shift selector and pressure control valve 
    - **speed selector spool** directs oil from charging pump to the speed clutches in transmission
    - **modulation relief valve** controls maximum clutch application pressure 
    - **load piston** provides clutch modulation which control how fast the clutch applied which means control speed or flow to avoid shock load on gear, and wear of clutches
        - clutches apply too quick cause shift shock
        - clutches apply too slow cause slippage
    - ratio valve: limit maximum pressure in torque converter when the engine is started with cold oil; thus it depends on viscosity of the oil will determine how the valve move. 
        - IOW, the valve prevent damage to tc caused by pressure rise during cold weather start-up.
- transmission clutches
    - steel reaction discs spline to housing
    - friction discs spline to ring gear
    - pistons are hydraulically applied, spring relief.
- transmission oil cooler
    - located @ the tc outlet 
- tc outlet relief
- leakage on seal of clutch piston cause slow application of piston

## automatic trans control system

- automatically shift based on machine ground speed and the operator's demand for power (throttle)

### hydraulic shift control system

- positions: applied, released, and hold
- governor provide machine ground speed (governor circuit)
    - convert rotational speed of trans output shaft to hyd pressure signal to control shift operations
        - balance bw centrifugal force generated by the weight and hyd pressure
    - driven by trans output shaft
    - zero pressure if output shaft does not rotate
    - low speed: low oil pressure; high speed: high oil pressure
- modulator pressure from throttle (modulator circuit)
    - controlled by modulator valve operated by linkage, cable or intake manifold pressure (spark ignition engine)
    - **delay upshift point** to allow the engine develop greater hp and momentum force before upshift
    - low throttle: high pressure; high throttle (wot): low pressure
- **shift signal valve** controls a relay valve that applies or release clutches (1-2, 2-3, etc.)
- control above factors, we have ability to control shift at different time
- impeller has pump but it supply oil for torque converter
- governor gets oil from clutch application circuit, (called governor pressure signal)
- clutch application pressure: 400psi, full flow, full pressure
    - low throttle, keep orifice closed (figure 27)
    - high throttle, orifice wide open (we don't want slippage)
    - orifice can be control by throttle linkage or vacuum line from engine intake manifold
- first and second are always the hard shift
- the release clutch is not fully release before the applying clutch engages
    - a momentary **engine lugging or slowing** of machine speed due to internal binding 
    - trans trying to **operate 2 speed @ the same time**
- the release clutch is release more quickly than the applying clutch engages
    - an engine **rpm flare**
    - a momentary freewheeling
- orifice control is used to control clutch release rates
- trimmer valve is used to control the clutch application's flow rate 
- erratic shifting can happen if scrapers as the wheels slip and regain traction multiple time
    - shift selector valve is introduced to override automatic upshift and downshift
    - application pressure is sent to the spring side of shift signal valves preventing it sends signal to relay valve which automatically upshift

### electronic shift control system

- speed sensor (governor circuit): (speed of trans output shaft) (AC)
    - slow speed: low voltage, low frequency
    - fast speed: high voltage, high frequency
- throttle position sensor (modulator circuit):
    - no throttle: high voltage
    - wide open throttle (WOT): low voltage
- solenoid: used PWM signal
    - proportioning

- abs light on, => don't go to lockup => burn transmission 
- too much clutches clearance will affect application
- input speed (engine speed), turbine speed, etc. used for clutch modulation and diagnosis
- shift solenoids energized by ECU based on ground speed and throttle 
    - they dirrects clutch application oil flow to the required application clutches

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
- no reverse:
    - c3 (5th) / c5 (1st) clutches
    - valve body / control circuit
    - electronic programming/sensors
- harsh shift or hard shift (shock the components, but good for clutches because it reduces wear on clutches )
    - modulator, it does not allow oil comming back to sump
- slow shifting (soft shift)
    - clutches are worn out
    - low oil flow, slowing piston to actuate
    - modulator valve
    - wrong oil, leaking seal
    - control circuit, valve body (spool slow to move, torque valve body wrong causing valve binding)
    - programming shift point (boost up or slow down)
- shuddering
    - lockup clutch: happen with light load, moderate acceleration, highway speed
    - transmission clutch packs
        - heavy/medium acceleration
        - leakage / pressure low; thus, don't have enough work to queeze the clutches
        - excessive hp
        - incorrect oil used
- noise
    - gear problems, bearing failure, (can be causing by lack of oil for a long time, metal-to-metal contact)
    - lack of oil
    - drive axle noise
    - overload
    - contamination
- **question to ask: this things comming out for what reason ?** if it is valve body problem, simple remove the valve body without pulling the whole transmission, or the problem can be in drive axle (like vibration from drive line can cause damage to clutches 'teeth will be hammered' and internal components). 
- plug all hydraulic lines upon servicing, BUT DONT FORGET TO REMOVE THE PLUG WHEN REASSEMBLY
- put snap ring in correct way make it easy to remove it later (the wider part face the housing) (tools: radiator hose pick) (trick: use a piece of cloth to prevent the snap ring fly away
- service chemical help to protect hand and make it easy to clean with only water (named: PR88)
- coned disc clutch should be put in same direction 
- torque valve body correct torque and sequence or bend the valve body easily
- check clutch clearance or height of clutches stack

# retarder

- rotor vanes strike the oil in the retarder housing cause resistance which transmitted to the driveline, thus slowing vehicle
- slow equipment down without using service/park brake
- convert kinetic energy to heat energy
- operation with high oil temp above 250F increase the oxidation of rate of oil and reduce the lub quality
- input retarder and (cat) brake saver (engine output retarder) (used engine oil)
    - get better result slowing because it can factor gear from trans (downshift trans during retarding)
    - mounted input shaft of transmission
    - doesn't care 'bout ground speed
    - compact (can build heat up fast)
    - how much braking is determined by how much flow into retarder. => aerate a lot!
    - lockup clutch in torque converter is required when input retarder and brake saver is on
        - retarder is mounted bw crankshaft flange and fw
    - use charging pump that supplies oil to tc/trans
- output retarders (allision):
    - mounted some where between transmission and rear axle
    - big heavy
    - retardation mode fill full oil, controlled how much braking by control the pressure inside the retarder
    - bigger sump, or larger cooler to handle heat
    - large spool valve
    - may use separated pump, res, cooler
- remote retarder
    - mounted on driveline
- may need more oil if there's a retarder. (engine or transmission oil)
- oil temp is higher than 275F can cause damage to the retarder

## components

- retarder rotor (rotating assembly)
- retarder housing (stator)
    - contain oil
- retarder control valve
    - direct oil supply to the retarder housing
    - manual, air-over-hyd, electronic control
- multi discs clutch (wet clutch)
    - provides quick application of retarder for a short period of time; then it's disengaged when retarder works
- accumulator is added to improve filling speed
- in normal use, the engine or exhaust brake is activate first; then retarder; improving service life of service brake

## retarder service

- check magnetic drain plug and filter element
    - shiny steel (pump wear)
    - aluminum (rotor wear)
    - rubber (seal or hose)
    - iron or steel chip (broken comp)
- incorrect oil level can cause prob

# clutch fundamentals and services (off-road)

- over-center clutch
    - used for stationary applications (ON/OFF) (e.i. pump)
    - no transmission: engine -> clutch -> stationary app (pump, etc.)
    - for driving accessory
    - clutch disc always rotate
    - 2 plates attached to the output
    - use more discs for more clamping force
    - lock to less 90 degree in order to get the most clamping force
    - clutch wear will increase clearance, thus effecting clamping force
    - just like brake, clutches don't need grease or oil, otherwise, losing friction
    - tapper roller bearing always required preload
    - clutches discs never touch the flywheel

# things to memorized 

- planetary gear set in CAT torque divider is lub by tc charge pressure
- the purpose of converter pressure relief valve is to prevent damage to tc components
- clutch pack clearance within a pw trans is important to ensure proper clearance bw discs when the clutch pack is not applied
- tc with fixed stator has 1 phase
- temp sending unit located in converter outlet port
- @ low engine speed, slippage on fluid coupling when no load is present is greatest
- tc mounted pto, tc housing is wet housing
- output speed sensor replace governer in electrical trans
- the valve in the governor was stuck in closed position, the result could be no up shifting
- top gear is the largest gear

