---
layout: post
title: electrical 2
categories:
  - elec, ihet3
...

- Body’s Ohm 150,000 600,00 Ohm
- Electric cause severe burn @ 200mA
- Cannot let go @ 15 - 20mA
- Ventricular fibrillation @ 100-200mA
- 1-8mA mild shock, let go @ will
- 8-15mA painful shock, may let go

# Review

## Ohm’s Law

$$V = IR$$

## Kichhoff’s Current Law

Sum of current into a node = sum of current out of that node
$$I = I1+ I2$$

**Period: one cycle (0 - 360 degree)**

*RMS: root mean square*

Vrms = 120 V
Vmax = Vrms / 0.707
Vint = Vmax * sineA

Period =  1 / f
f frequency (Hz)

## Vac + Vdc signals
When an AC sine wave and a DC source are placed together, the DC source is used as the AC sine wave reference center line.

$$V_{AVE} = Voltage (average) = V_{DC}$$
$$V_{RRMS} = Voltage Ripple Root mean square = V_{AC}$$
$$V^2_{RMS} = V^2_{DC} + V^2_{AC}$$

# Circuit elements

## Pushbuttons and switches

### Pushbutton:

- One of the most used symbols in control schematics
- Contains both movable and stationary contacts
- NO - normally open
- NC - normally closed
- Double acting pushbutton: contains both normally open (NO) and normally closed (NC) contacts. -- dash line represents a mechanical connection

### Push-pull buttons:

- Are used to provide the start and stop functions in one push button (ex: emergency stop)
- Eliminates need for space for a second push button

### Lighted push buttons:

- Used to indicate a specific status or operation of equipment
- Generally used to indicate motor running, stopped or tripped on overload

### Switches (symbols):

NO - normally open switch
NC - normally closed  switch

## Coil

- Represents coil of a relay, contactor or motor starter

## Contacts

- NO - normally open
- NC - normally closed

## Overload Relays

Overloads are designed to protect the motor from overload conditions
Typically overload relays are designed to open the circuit when the current becomes 115% to 125% of the motor full load current.
They must have some means of sensing motor current
They must have some type of time delay (motors typically draw about 300% to 800% of full load current when started)
Divided into two sections; the current sensing section and the contact section.
OLHTR = overload heater

## Manual Starter

The operator must go to the location of the starter to initiate any change of action

### Single-Pole manual starter

### Double-pol manual starter

As the overload heater (OLHTR) passes current, they heat up; if too much current passes through (which is an overload condition); the OLHTR causes a mechanical mechanism to trip and open the switch contacts disconnecting the motor from the power line.

## Automatic Starter

A sensing pilot device is used with a manual starter to allow for automatic operation. (newer are electronic)

## Relay

Are electro mechanical switches that contain auxiliary contacts
Typically relays are used for small control applications (ex, 12V, 24V, 120V equipment)
Contains contacts and a coil
Used in single phase applications commonly

## Contactor

Are similar to a replay but used for higher voltage and  current applications ( ex: voltages 240V and above)
Mainly used in 3 phase applications

## 2 types of control systems

### 2 wires: (or low voltage release)

Consists of typically on pilot device and output device connected directly
Maintains original state before any action is applied to the pilot device (ex: sump pump, lights in a house)
Low voltage release: the electrical devices continue to operate in their original state if power is lost. Examples:: sump pump, lights

### 3 wires: (or low voltage protection)

Consists of more than one pilot device connecting to one or more output devices
MC symbols : they have directly relations (seal-in or hold-in contact & motor)
Low voltage protection: the electrical devices revert back to the original state of the circuit, but the output is de-energized upon a power failure. (Example applications: conveyors, starter circuit for an engine

## Timing Relays

Two general classifications: on-delay relay & off-relay
On delay Relay (DOE - delay on energize); Applications: fan in a car on a cold day; lights; motors applications
Off delay Relay (DODE - delay on de-energize); Applications: Cooling fan, radio, oven in house, garage door light, computer monitor; car light after power off and close door.

## Pressure Switches

Used in systems where sensing pressure of pneumatic or hydraulic systems

## Float switches

Typically used when a pump motor must be started and stopped when water (or liquid) level change.

## Flow switches

Used to detect the movement of air or liquid through a duct or pipe

## Limit switches

Used to detect when an object is present or absent from a particular location
Can be activated by motion of a machine or the presence or absence of a particular object

## Temperature (sensing) switches

Temperature measurements are done through sensing devices
Sensing devices is not like a simple switch as it involves expansion and contraction of two different materials

## Conductors
Have 1 to 3 valence electrons in their outer shell
Can transmit electricity easily

## Insulators

Have 5 or more in the outer shell
Not readily transmit electricity

## Semiconductors

Has 4 valence electrons in the valence shell
Germanium (Ge) & silicon (Si) are used to create semiconductors

## Doping

Take a pure (intrinsic) material and mix with an impure material in small quantities

## P-N junction

Typically the voltage drop across the junction will be 0.7V

## Diode

Made up of P-N junction, and allows current to flow in one direction
 current that flows through the diode when the diode is conducting is known as biased.

## Depletion Region

Also known as the barrier between P-N materials.

## Barrier Potential

Is the voltage required to allow current flow through the barrier.
This is roughly around 0.65 → 0.7 V

## PIV - (Peak Inverse Voltage)

This is the maximum reverse voltage that can be applied to a diode before it breaks down.

## Diode

P-side - Anode (A)
N-side - Cathode (K)j

# Topics in First exam:

1. Resistors, capacitors, and inductors: basic questions series, parallel
2. Voltage, current, impedance
3. Power (P - W), Reactive Power (Q - VARS), Apparent Power (S - VA)
4. Safety basic questions
5. Control schematics: 2-wire (low voltage release), 3-wire system (have low voltage protection ), basic questions
6. Analysis a control circuit: give steps
7. Identify control devices
8. Capacitor pass current in AC&DC
9. Relays, contactors
10. Timing relay, float, pressure, temperature, limit, flow switches.

# Retifier

Rectifier is a device or circuit that changes AC to DC

## Half wave rectifier

- It is the simplest rectifier
- Consist of an _AC source_, _diode_ and _load_ connected in series
- easier to create, cheap

**Diagram here:**

$$I_{Diode} = I_{Load}$$
$$V_{peak} = {V_{source} \over 0.707}$$
$$V_{DC} = V_{peak} * 1/\pi$$
$$PIV (Peak\ Inverse\ Voltage) = V_{peak}$$
$$f_{load} = f_{supply}$$
$$I_{DC} = {1 \over \pi} * I_{peak}$$


**Ripple factor** is how much AC is left after the conversion to DC; thus efficiency of conversion to DC.

$rf = 121\%$

**Example:**

To find ripple factor use this equation

$$rf = {VAC(load) \over VDC(load} * 100 \%$$

- Step 1: Find VDC(load)

$$VDC(load) = Vpeak * 1 / pi = 120V/0.707 x 1/pi = 54V$$
$$VAC(load) = Vsource x square(2) = 120V$$
$$VAC(load) = 169V$$
$$rf = 169V/54V x 100 = 121$$

## Full wave (single phase) rectifier

- two specific types of full wave: center tap 1 & full wave

### Center tapped full wave rectifier

- very popular, used for low voltage dc output where transformer is required
- very inexpensive to setup
- consists of half wave rectifier duplicated
- examples: battery chargers for recreational vehicle.

**Diagram here**

$$I_{load} = 2*I_{diode}$$
$$V_{peak} = {V_{source(sec)} \over 0.707}$$
$$V_{DC} = {2 \over \pi }*V_{peak} $$
$$PIV = V_{peak} (entire\ secondary) = 2 V_{source}$$
$$f_{load} = 2 * f_{supply}$$
$$rf = 48\%$$

### Full wave bridge rectifier

- provides rectification like center-tap but it utilizes 4 diodes
- manufactures make them with all 4 diodes in one package
- use for high voltage applications, reliable
- expensive

**Diagram**

$$V_{peak} = {V_{ac(source)} \over 0.707}$$
$$I_{load} = 2I_{diode}$$
$$V_{DC} = {2 \over \pi} * V_{peak}$$
$$PIV = V_{peak(source)}$$
$$f_{load} = 2 * f_{supply}$$
$$rf = 48\%$$

**Problems**
short -> short the supply
open -> half way rectifier

## Three Phase Half Way Rectifier

- majority of industrial applications need large amounts of dc power
- used for driving a dc motor, or as input to a VFDs (variable frequency drive)

**Diagram**

**Wave form**

$$3Idiode = Iload$$
$$Vpeak = Vphase / 0.707$$
$$Vdc = 0.827Vpeak (82.7\% if Vpeak) (this is be given!)$$
$$PIV = Vpeak(line voltage)$$
$$fload = 3 * fsupply$$
$$rf = 17.7\% (better than half, full wave rectification, lower number, better)$$

## Three phase full wave bridge rectifier

- very common in industry for high voltage & current application

**Diagram**

$$Vdc = Vpeak * 3/pi = 0.955 Vpeak$$
$$Vpeak = Vline/0.707$$
$$3Idiode = Iload$$
$$PIV = Vpeak(line voltage)$$
$$fload = 6fsupply$$
$$rf = 4.5\%$$

## RC - resistor capacitor circuit

- Add capacitor to improve rf, close to zero; thus improving dc power output
- Capacitor is almost like a short
- Charge in positive cycle
- Discharge in negative cycle; thus improving dc

T (period for charging) = RC

LAB 6
       Theory  Measurement
$$Vave = 0 V$$
$$Vrms = 120V$$
$$Vbd = Vave = 2/pi Vpeak$$
$$Vab = Vave (don't care)$$



## Summary

- Half way

![Rectified Output Waveform](/img/electrical-2/halfway.gif)

$$
I_{load} = I_{Diode}\\
V_{peak} = {\sqrt{2}}*{V_{source}} \\
V_{DC}   = 1/\pi*V_{peak}\\
PIV      = V_{peak}\\
f_{load} = f_{supply}\\
rf = 121\%\\
$$

- Center-tapped full way

$$
I_{load} = 2*I_{Diode}\\
V_{peak} = {\sqrt{2}}*{V_{source}} \\
V_{DC}   = 2/\pi*V_{peak}\\
PIV      = 2*V_{source}\\
f_{load} = 2*f_{supply}\\
rf = 48\%\\
$$

- Bridge full way

$$
I_{load} = 2*I_{Diode}\\
V_{peak} = {\sqrt{2}}*V_{ac(source)}\\
V_{DC}   = 2/\pi*V_{peak}\\
PIV      = V_{peak}\\
f_{load} = 2*f_{supply}\\
rf = 48\%\\
$$

- Three phase half way

$$
I_{load} = 3*I_{Diode}\\
V_{peak} = \sqrt{2}*V_{phase}\\
V_{DC}   = 0.827*V_{peak}\\
PIV      = V_{peak}\\
f_{load} = 3*f_{supply}\\
rf = 17.7\%\\
$$

- Three phase bridge full way

$$
I_{load} = 3*I_{Diode}\\
V_{peak} = \sqrt{2}*V_{line}\\
V_{DC}   = 0.955*V_{peak}\\
PIV      = V_{peak}\\
f_{load} = 6*f_{supply}\\
rf = 4.5\%\\
$$

*Note*:

$$
V_{RMS} = V_{Source}\\
I_{load} = I_{DC}
$$

# Zener Diode

- special device designed to operate in reverse polarity
- when this diode operates in this reverse direction, it is known as the Zener region.
- usually if a diode operates at a high voltage in the Zener region, it would be destroyed; but the zener diode is designed to operate in this region.
- the supply voltage must be greater than the voltage of the Zener diode in order for it to work.
- maintain 12V voltage

**Graph**:
![Zener diode graph](/img/electrical-2/zenerdiodegraph.jpg)

**symbol**:


**Example**:

![example 1](/img/electrical-2/diodeex1.jpg)

Find I_2 for the circuit

- Step 1: find the resistance for R2 and R3
$$R_{2,3} = R_2 + R_3 = 20 + 1000 = 1.2k\Omega$$
- Step 2: Find
$$I_{2,3} = {V_{2,3} \over R_{2,3}} = {V_{z} \over R_{2,3}} = {12V \over 1.2k\Omega} = 0.01A = 10m$$
- Step 3: If there is 12 V_dc for the paprallel branches, that means that R_1 sees
$$(20V - 12V) = 8V = V_1$$
$$I_1 = I_T = {V_1/R_1} = {8V / 100\Omega} = 80mA$$
- Step 4: To find current though the zener diode, we subtract I_{2,3} from I_1
$$I_1 = I_2 + I_{2,3}$$
$$I_2 = I_1  - I_{2,3}$$
$$I_z = 80mA - 10mA = 70mA$$

# Transistors (BJT: Bipolar Junction Transistor)

- made by connecting 3 pieces of semiconductor material
- there are two basic types of transistors: NPN and PNP
- it is an electric valve that allow current flow through the collector and emitter, when where is a current flow through the base & emitter
- a small current flow of say 1mA through the base and emitter, can have the collector & emitter flow around 100mA
- with an increase or decrease in base & emitter current, the collector & emitter current also increase and decrease
- Applications
    - switches
    - amplifiers

- 3 elements: base, collector, and emitter; base->emitter is the trigger for flow in collector & emitter.
- NPN: Base(+); PNP: Base(-)
- the emitter is only on the other side of arrow
- current flow from P to N
- need to switch batteries polarity when changing NPN to PNP

**Physical layout**:

![npn-pnp](/img/electrical-2/npn-pnp.jpg)

- NPN (more common)

- PNP

# SCR (Silicon Controlled Rectifier)

- thyristors, specifically SCRs are the most used and oldest semiconductor power control devices in industry today
- used in primary power control in all DC motors, and in large AC motors drives
- used in mining equipment
- is a three terminal, 4 layers semiconductor device primarily used as a switching element or device
- SCR is a rectifier, only allows current flow in one direction like a diode
- basic difference is that it will not conduct current or forward bias until its gate receives a positive pulse of current
- **Commutation**: turning an SCR OFF after it has been conducting current, 3 ways to commutate SCR
    - Natural commutation: push NO button, creating a short across the SCR, then the SCR is OFF because of the short
    - Class F commutation: the SCR is turned OFF automatically by AC source, it need to be turned on after each AC cycle
    - Forced commutation: by using capacitor connected in para with the CSR

- Summary:
    - the SCR is OFF, until an initial gate current pulse
    - the SCR is ON with a gate pulse
    - once its ON, the SCR remains on until the current flow through the anode and cathode is so low that it drops out of conduction

**Symbol**

![scr](/img/electrical-2/scr.jpg)


**EXAM: everything up to this point**

# inverter

- convert DV voltage into ac voltage

![ivtr](/img/electrical-2/ivtr.jpg)

# transformer

- have a primary and secondary side with typically a steel core.

- laminations are used to reduce eddy current losses between each of the core sheet elements

- the high side of transformer (more windings) is denoted as H

- the low side of transformer (less windings) is denoted as X

- there are 3 functions for a transformer

    - H side: high number of windings; X side: low number of windings

    - primary side's connected to the source; secondary side's connected to the load.

    - High side has higher resistance; low side has lower resistance.

    - *step down*: the voltage is decreased as the H has the source voltage and the X side is connected to the load

    - *step up*: the voltage increase as the X side is connected to the source and the H side is connected to the load

    - *isolation*: the voltage of both the H & X sides is the same, but the two side are electrically isolated from each other (for protection purpose, don't create damage on the other side )

    - Transformers are rated in VA (Volt-Amps)

    - N is number of windings; a is turns ratio

    $$
    a = {V_p \over V_s} = {V_{source} \over V_{load}} = {N_p \over N_s} = {I_s \over I_p}\\
    V_pI_p = V_sI_s\\
    VA_p = VA_s\\
    $$

    $$
    N_p = 100; N_s = 50; V_p = 120V; I_p = 3A\\
    { 120 \over V_s} = {100 \over 50}\\
    V_s = 60V\\
    {I_s \over 3 } = {100 \over 50}\\
    I_s = {300 \over 50} = 6 A
    $$


