# 1224 Amplifier

![layout](layout.png)

This repository contains the source files for a tube amplifier as I go through the process of designing and building the prototype.

## Background

The origins of this amplifier begin with a [Philco model 1224](https://www.vintageradio.co.nz/model/philco/1224). I originally picked up a non-functioning unit with the intent of restoring it to a working state, but it very quickly became apparent that this wouldn't be possible. I did manage to salvage a working power transformer, output transformer and speaker from the otherwise useless components and chassis.

After tracking down a [schematic of the original radio](https://www.vintageradio.co.nz/static/images/models/philco/1224/Philco_1224_schematic.png), the new plan became to try and build a guitar amplifier instead.

I am a complete novice at this electronics thing, so this repository also serves as a record of my progress in learning and (hopefully!) understanding.

## Provided files

![schematic](schematic.png)

- [1224.sch](1224.sch) - the schematic, in [Qucs-S](https://ra3xdh.github.io/) format.
- [schematic.png](schematic.png) - an image render of the schematic, as seen above.
- [bom.csv](bom.csv) - a simple Bill of Materials.
- [1224.diy](1224.diy) - the chassis layout in [DIY Layout Creator](https://github.com/bancika/diy-layout-creator) format.
- [layout.png](layout.png) - an image render of the layout, as seen at the top of this README.
- [layout.pdf](layout.pdf) - a vector PDF render of the same layout.

## Design goals

### Power

In my lack of experience, I've used as much as possible from existing
schematics. The power supply, rectification, filtering and output stages have been lifted almost exactly from the original schematic. The only significant deviations from the original in this section are:

- replacing the three capacitor can with individual capacitors of the same value and rating; and
- replacing the 1500 Ω, centre-tapped power resistor with two 750 Ω resistors (of appropriate power dissipation) in series.

This is simply to reduce costs and make the final amplifier more serviceable in future.

### Preamp

The preamp is comprised of a chain of cascading gain stages, provided by two 7F7 dual triode tubes. The circuit input could be described as a single-jack implementation of in a style typical of many vintage Fender amplifiers:
- R2 (68K) provides grid stopper duties for the first gain stage; and
- R1 (1M) provides a high impedance to the source.

A potentiometer is inserted between the first two gain stages (to act as a Gain control), and another potentiometer is inserted between the last gain stage and the power tube grid (to act as a Master Volume).

A three band tone circuit - lifted from the classic [Fender Bassman (5F6-A)](https://en.wikipedia.org/wiki/Fender_Bassman) and modified only very slightly - is added after the third gain stage, with the last gain stage intended to reclaim some of the losses incurred by the tone circuit.

### Summary

What I'm left with is an untested prototype circuit which should **not** be considered safe/accurate/working/usable in any capacity.
