---
layout: post
title: powershift and automatic transmission
categories:
  -
---

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
| :---------------- | :---: | :---: | :---: | :---: | :---: |
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

1. after pump may have priority flow control which redirect oil to brake and steering first (then send oil to trans after satisfying that first), such as dozer (or we must have other pump for that)
2. shift selector valve (valve body, basically a dcv) 
3. for example we are in neutral, c5 locked up, oil will be sending to clutch pressure regulator valve (pressure increase to 400psi, then regulator valve open)
4. oil will be feed to tc relief valve (control maximum system pressure, just like system relief)
5. oil send out from tc go to filter and cooler then back to lub circuit (don't need to be a high pressure circuit) (which lub trans)

