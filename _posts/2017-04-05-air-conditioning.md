---
layout: post
title: air conditioning
categories:
  -
---
- sw
    - The number of poles* on a switch defines how many separate circuits the switch can control. So a switch with one pole, can only influence one single circuit. A four-pole switch can separately control four different circuits.
    - A switch throw-count defines how many positions each of the switch poles can be connected to. For example, if a switch has two throws, each circuit (pole) in the switch can be connected to one of two terminals.
## AC system

- heat movement
    - heat moves from a hotter area to a colder area.
    - conduction, convection, and radiation
- heat measurement
    - intensity: $$C = (F - 32) * {5 \over 9}$$
    - quantity: BTU, J
- latent heat (hidden heat) is the heat absorbed or given up upon changing state
    - vaporized @ vaporator(lower pressure): liquid +BTU (blow hot air in the cab to the vaporator) = vapour
    - condensed @ condenser (high pressure): vapor -BTU (fan remove heat) = liquid
- @ low pressure, liquid boil at a lower temperature
    - low pressure - boiling vapour - compressed high pressure - liquid +BTU
- superheat
    - require to assure the compressor is protected from liquid refrigerant.
    - compared low pressure side with evaporator outlet temp
    - specs 8 - 12F
- subcooling
    - compared high pressure side with condenser outlet temp 
    - specs 12-21F
- refrigerant
    - common R-134a
    - mineral oil (MO) does not mix with R-134a (not compatible)
    - polyol ester (POE) & Polyalkylene glycol (PAG) can be mixed with R-134a
    - MO can not mix with PAG
- AC events
    - expansion
       - liquid expanding from high pressure side 124psi(100F) to low pressure 30 psi (90F)
    - evaporation
        - pressure is lower, so liquid change to a vapor, thus absorbing heat 
        - warm area cooled
    - compression
        - raise pressure and temp of the vapor
        - 124 psi, 220F
    - condensation
        - cool vapor to 100F
        - vapor change to liquid
- heat it up => pressure increases
- AC ref: http://www.central-air-conditioner-and-refrigeration.com/basic-refrigeration-cycle.html
- pressure and boiling point relationship
    - lower pressure, lower boiling point
    - higher pressure, higher boiling point
- perfect vacuum: 30, cannot get more than that
- 30 in of Hg = 760,000 microns 
    - 500 microns are expected
- refrigerants
    - no color, slight odour
    - non-toxic, non corrosive, non-flammable
    - most common nowsaday, 1234yf (move around 55-60BTU/lb)
    - Duracool 12a or HC-12a (crap!), flammable
    - R-12 (freon) (50BTU/lb) ozone depletion (used mineral oil, use good hose), R-134a (90 BTU/lb) green gas
        - to change the use of R-12 to R-134a, we change the fitting, different size of orifice if needed 
        - 1995 banned in North America
        - mineral oil based
    - r-134a (smaller molecues) 
        - non ozone depletion
        - green gas gas contributor
        - lub: poly alkaling glycol (P.A.G) (seperated with refrigerants) (for hot environment)
        - poly ol ester (mix with everything, use for top off) (will get hot fast!)
- accumulator have a hole to pick up oil circulating the system
- condenser subcooling
    - proper change: 180in 150out
        - outlet temp: 20-50F cooler
        - subcool happens in condenser, dryer, hose
    - under charge: 180in 80out
        - the change of state is completing too far from the outlet
    - overcharge: 180in 180out
        - the change of state is not completed inside the condenser
        - subcooling is not happening inside the condenser
- evaporator superheat
    - proper charge: 32-39F
        - outlet is 2-10F warmer
        - the change of state is completing close to outlet 
    - undercharge 32-62F
        - the change of state is completing too far from outlet
        - superheat in evaporator, suction
    - overcharge: 32in-29out
        - the change of state has not completed inside the evaporator
        - the eva does not warm the vol of refrigerant fast enough
- txv does not have acc to prevent liquid enter compress, do not overcharge
- ccot does not have dryer

## AC Control system

- If Low pressure sw should be on low side, and High pressure sw should be on high side, we can not run ac system with low refrigerant.
- If we have low refrigerant and low-high pressure sw (trinary) on high side, we can still run ac system
- active control
    - engine coolant water valves
        - flow restricter located in engine coolant water valves slows the coolant down, so heat has time to transfer to the cab
        - seized open coolant water valve causes the truck cab to remain very warm even when the AC is operating
    - magnetic clutch
        - black coil lead wire: 12V
        - green coil lead wire: 24V
- passive (automatic) control
    - thermostatic sw:
        - when the evaporator core is warm, the sw closes the contact, engaging the compressor
        - when the evaporator core is closed to freeze temp, stop the compressor; the heat will warm and defrost any frozen moisture
        - fixed sw senses 32F (sw opens) -38F (sw closes)
        - adjustable can reach 50F for closing point
    - low pressure sw
        - normally open valves
        - 24psi open; 34psi close
        - located in low side on acc, protect compressor from low refrigerant pressures due to blocked expansion valve or lack of refrigerant
        - located in high side on receiver/dryer, sense low pressure from high side and ambient temp is too cod
    - clutch cycling sw (ccot) (low pressure sw)
        - protect compressor from operating with low refrigerant pressure & no oil circulation
        - located on accumulator 
            - 24psi, 32F, sw open, stop compressor, defrost evaporator 
            - 48psi, 39F, sw close, start compressor, cool evaporator
    - high pressure cut-out sw
        - sense high side
        - normally close when pressure is normal
        - cut in @ < 250psi, start compressor
        - cut out@ >= 350psi, stop compressor
        - must lower than pressure relief valve (fusible plug)
        - can use to control condenser fan & radiator shutter systems
            - condenser fan kick in when condenser does not receive enough cooling ram airflow to keep the pressure with normal limits
    - binary sw (low/high pressure sw)
        - provide slow and high pressure protection
        - located bw condenser and expansion device (on dryer)
    - trinary sw
        - located bw condenser and expansion device (on dryer)
        - high-low temp sense: 2 terminal control the clutch
            - NO
            - low: open @ 15-28psi 
            - high: close @ 40psi
        - sense high side pressure
            - NC
            - low: close @ 80-125psi
            - high: open @ 270-330psi
        - mid range: 2 terminal controls condenser fan
            - low: open @ 35-60psi
            - high: close @ 200-230psi
    - refrigerant solenoid valve
        - direct refrigerant to second evaporator's expansion device
        - open when sleeper compartment call for cooling and cab has to be in operation
    - blower motor and fans
        - "single or double shaft" motor
        - "single or double entry" blower wheels 
- AC management system
    - control module
    - monitor (input)
        - high / low pressure
        - thermostatic sw
    - control (output)
        - condenser fan (how long is engaged depending on vehicle speed and how high the pressure is)
        - compressor clutch
- automatic temperature control
    - monitor (input)
        - cab temp sensor
        - fresh air temp sensor
        - evaporator temp sensor
    - control (output)
        - heater water valve
        - blower fan speed
        - compressor clutch
- manual climate control HVAC system (temperature blend air door system)
- air distribution system
    - settings
        - fresh air door setting: recirculation and fresh air
        - temp setting: red and blue
        - airflow direction: panel, panel & floor, floor & defrost, and defrost 

    |---
    | | max cooling | max heating | max defrost| normal cooling | floor and defrost heating | cab ventilation
    |---
    | blow speed | max | max | max | lowest | second speed | second speed
    | heater water valve | closed | opened | opened | **partly opened** | opened | **partly opened**
    | fresh air intake | closed | closed | closed | closed | closed | opened
    | cab recirculation air inlet | opened | opened | opened | closed | opened | closed
    | panel outlet | opened | opened | closed | opened | closed | opened
    | floor outlet | opened | opened | closed | closed | opened | opened
    | defroster outlet | closed | closed | opened | closed | opened | closed
    | compressor clutch | engaged | disengaged | **engaged** | engaged | disengaged | disengaged
    | AC sw | on | off | **off** | on | off |  off
    | ---

- sleeper compartment
    - heating: electronically controlled coolant valve installed on return side of coolant on sleeper side
    - cooling: electric refrigerant solenoid valve installed after dryer on sleeper side
    - fuel-fired **air** heater (draw 2A/hour) use to reduce premature engine wear on parking truck for sleeping
    - fuel-fired coolant heater
        - draw dc
        - help engine start up
        - warm sleeper compartment
        - some sense battery voltage and not operate if less than 10.5V
    - aux power units
        - warm by heat from aux engine
        - cool by aux driven air ac compressor
- use fuse protected jumper wire override the low pressure sw, if clutch engages
    - low refrigerant
    - faulty low pressure sw
    - the refrigerant is too cold to create enough pressure to closed the sw