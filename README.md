# Analog-Voice


This repository will hold my analog voice modules.

The plan is to design and build a cheap analog (mainly subtractive) voice that can be built very cheaply or even
ordered via the Chinese PCB Assembly services.

Please read below for the status of these designs. Some are works in progress and some are completed.

- - - -

I made a 3d-printed case with a dc-dc converter (£7.50) to test them:
![case](https://github.com/forestcaver/Analog-Voice/blob/master/images/017-modular_3dcase.jpg)

- - - -

## 3340 VCO ##

![3340 vco](https://github.com/forestcaver/Analog-Voice/blob/master/images/3340_vco.jpg)

8hp.

3340-based oscillator with hard and soft sync, linear and exponential fm (with fm cv attenuverter), pulse width (knob and cv with attenuator). Reverse polarity protection. Uses an as3340 chip.

The 3340 soft sync only works on a falling edge so a ramp waveform is ideal eg /| (and not |\ ). Hard sync works on rise and fall. The sync switch is an on-off-on switch (centre position turns off sync)
The 3340 fm knob is an attenuverter. The fm switch selects between exp fm (dc coupled) and lin fm (ac coupled). It's an on-off-on switch so the centre position turns off fm (handy for wiggling). The lin fm is ideal for audio rate modulation.
The 3340 pwm input takes 0-5v for min to max effect. The pwm pot is an attenuator, pwm is added to the pw pot.
The outputs of the 3340 are all normalised to just below 10v p-p, all outputs are bipolar.
Calibration is as per the cem3340 datasheet. ie set v/oct scaling, then do the hi-osc adjustment if necessary.
Mine tracks within one cent over 6 octaves.

- - - -

## 3320 LPF ##

![3320 lpf](https://github.com/forestcaver/Analog-Voice/blob/master/images/3320_lpf.jpg)

4hp.

4-pole (24db/oct lpf) with fm cv attenuverter, can self oscillate. Reverse polarity protection. Uses an as3320 chip.

The fm knob is an attenuverter
The 3320 has quite an aggressive resonance which kicks in at about 1/3 of the turn of the pot. You can easily adjust this by using different values for r25. One technique to find what you like could be to wire a 100k pot to the two pads, play with the module and set the resonance how you want, then desolder, read the resistance and solder a resistor of that value. You can refer to the resonance curve in the datasheet as well to see the response curve. I like it quite aggressive and have chosen about a 50k (ie 49.9k) resistor to get full range of resonance.
Calibration - turn resonance up to self-oscillation and adjust the tracking to get the best you can. It's not temperature corrected or perfect but is pretty reasonable. Before you calibrate, let it warm up for a few minutes ideally. It will track within 1 cent over two octaves.

- - - -

## Phones (Headphone Amp) ##

![Phones](https://github.com/forestcaver/Analog-Voice/blob/master/images/AJH_Phones.jpg)

4hp

NJM4556 based headphone amp. This is essentially the power section from the nwavguy o2 headphone amp. It has
a very low output impedance (~1 ohm) so can drive even low impedance headphones. It can deliver a high power
(utilising two sections of the njm4556 per channel) so can drive 600 ohm impedance headphones with no problem.
There is a high pass filter on the input to block dc.

- - - -

## LPG ##

![LPG](https://github.com/forestcaver/Analog-Voice/blob/master/images/AJH_lpg.jpg)

4hp

Buchla-esque lpg. Uses an analog switch ic to select between filter / lpg / vca so that a mechanicaly
simple spdt on-off-on switch can be used instead of a 3pdt mechanical switch. Filter has added resonance control.

- - - -

## HPF ##

![HPF](https://github.com/forestcaver/Analog-Voice/blob/master/images/3320_hpf.jpg)

4hp

4-pole (24db/oct hpf) with fm cv attenuverter, can self oscillate. Reverse polarity protection. Uses an as3320 chip.
Very similar to the lpf (above) with a simpler set of components around the 3320 but has similar features (apart from,
obviously, being a high pass filter!)

- - - -

## Dual ASR ##

![DASR](https://github.com/forestcaver/Analog-Voice/blob/master/images/AJH_ASR_01.jpg)

4hp

Dual ASR (Attack/Sustain/Release) in 4hp. Gate A normalled to Gate B. Reverse polarity protection. Uses two as3310 chips.

- - - -

## Dual VCA ##

![2V](https://github.com/forestcaver/Analog-Voice/blob/master/images/013-modular_ajh_vca1.jpg)

4hp

Dual VCA in 4hp. (Derived from two sections of Mutable Instruments Veils). Can chain an unlimited number together to make a huge multi-channel VCA or VC-mixer. Uses a 2164 chip.

- - - -

## Wasp ##

![2V](https://github.com/forestcaver/Analog-Voice/blob/master/images/018-modular_ajh_wasp.jpg)

4hp

Wasp filter in 4hp.

- - - -

## ADSR ##

![2V](https://github.com/forestcaver/Analog-Voice/blob/master/images/020-modular_ajh_adsr.jpg)

4hp

a100m ADSR in 4hp.

- - - -

## LPF 2 ##

![2V](https://github.com/forestcaver/Analog-Voice/blob/master/images/022-modular_ajh_lpf2.jpg)

4hp

ssi2144-based filter in 4hp with attenuverter on FM input.

- - - -

## Module Tester Module ##

![2V](https://github.com/forestcaver/Analog-Voice/blob/master/images/024-modular_ajh_module_tester.jpg)

SMT module tester module with four added precision voltage outputs (set with trimmers).

- - - -

## Dual polarising VCA ##

![2B](https://github.com/forestcaver/Analog-Voice/blob/master/images/2B_01.jpg)

4hp

Dual polarising VCA (based on Mutable Instruments Blinds). Multiple modules can be chained together.


- - - -

## Matrix Mixer ##

![2B](https://github.com/forestcaver/Analog-Voice/blob/master/images/025-modular_ajh_mm.jpg)

14hp

Matrix mixer in 4hp. Control knobs for each column can be selected to be bipolar (attenuverting) or unipolar (attenuating).
You can select a 5v offset to be normalled to input 4 as well.

- - - -
 
## TZFM VCO ##

![TZFM](https://github.com/forestcaver/Analog-Voice/blob/master/images/027-modular_ajh_tzfm.jpg)
![TZFM2](https://github.com/forestcaver/Analog-Voice/blob/master/images/028-modular_ajh_tzfm.jpg)

8hp

TZFM analog VCO using the ssi2130 analog chip. Hard/soft sync (can be turned off with switch in middle position.
PWM attenuator (0-5v cv input), exponential FM with attenuverter, linear FM with attenuator. Hard/soft sync.
Jumpers allow you to change the behaviour of PWM (either the leading edge of the pulse is constant and the trailing edge
occurs at varying times or both leading and trailing edges of the pulse change). Jumpers also selct whether to use FM or PM.
(Note that this is quite a dense build!)


- - - -


## My Other Modules On GitHub ##

### Minx ###

4hp buffered mult (three sections from MI Links)

![minx](https://github.com/forestcaver/Minx_AJH/blob/master/minx_01.jpg)

[Minx](https://github.com/forestcaver/Minx_AJH "Minx_AJH")

### Jinx ###

4hp triple S+H/noise

![jinx](https://github.com/forestcaver/Jinx/blob/master/jinx_01.jpg)

[Jinx](https://github.com/forestcaver/Jinx "Jinx")

### Benjolin ###

0603 version of Rob Hordijk's Benjolin (with kind permission from Rob)

![Benjolin](https://github.com/forestcaver/Benjolin/blob/master/569-modular_benjolin.jpg)

Strictly for non-commercial use:

[benjolin](https://github.com/forestcaver/Benjolin "Benjolin")

- - - -

## Planned Modules ##
### Completed - not yet uploaded ###
- TZFM VCO (8hp, ssi2130-based) + 8hp expander

### In Design and Prototyping ###
- Serge volatage-controlled slew (testing now)
- MIDI Thru box
- Contact mic preamp
- Quad digital lfo and envelope generator
- vca (3360)
- vcadsr (3310)
- Wavefolder
- Distortion module
- Delay module
- Updated Benjolin

### Planned ###
- quad adsr (3310)



Licence: CC-BY-NC-SA 4.0, unless otherwise stated in the individual repositories
