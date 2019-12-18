# Analog-Voice
This repository will hold my analog voice modules.

Currently, there is a 3320-based lpf and a 3340-based vco.
Both prototypes work well. However I have yet to build the (hopefully) final versions.
For both of these modules, I have taken inspiration and designs from TINRS, Mutable Instruments and the datasheets for both the Alfa chips and the original CEM chips.

Notes - 3340:

![3340 vco](https://github.com/forestcaver/Analog-Voice/blob/master/3340_vco.jpg)

8hp.

3340-based oscillator with hard and soft sync, linear and exponential fm (with fm cv attenuverter), pulse width (knob and cv with attenuator).

The 3340 soft sync only works on a falling edge so a ramp waveform is ideal eg /| (and not |\ ). Hard sync works on rise and fall. The sync switch is an on-off-on switch (centre position turns off sync)
The 3340 fm knob is an attenuverter. The fm switch selects between exp fm (dc coupled) and lin fm (ac coupled). It's an on-off-on switch so the centre position turns off fm (handy for wiggling). The lin fm is ideal for audio rate modulation.
The 3340 pwm input takes 0-5v for min to max effect. The pwm pot is an attenuator, pwm is added to the pw pot.
The outputs of the 3340 are all normalised to just below 10v p-p, all outputs are bipolar.
Calibration is as per the cem3340 datasheet. ie set v/oct scaling, then do the hi-osc adjustment if necessary.
Mine tracks within one cent over 6 octaves (!)

Notes - 3320 lpf:

![3320 lpf](https://github.com/forestcaver/Analog-Voice/blob/master/3320_lpf.jpg)

4hp.

4-pole (24db/oct lpf) with fm cv attenuverter, can self oscillate.

The fm knob is an attenuverter
The 3320 has quite an aggressive resonance which kicks in at about 1/3 of the turn of the pot. You can easily adjust this by using different values for r25. One technique to find what you like could be to wire a 100k pot to the two pads, play with the module and set the resonance how you want, then desolder, read the resistance and solder a resistor of that value. You can refer to the resonance curve in the datasheet as well to see the response curve. I like it quite aggressive and have chosen about a 50k (ie 49.9k) resistor to get full range of resonance.
Calibration - turn resonance up to self-oscillation and adjust the tracking to get the best you can. It's not temperature corrected or perfect but is pretty reasonable. Before you calibrate, let it warm up for a few minutes ideally.


Planned modules:
- 4hp 24db/oct hpf in 4hp
- dual vca
- envelope generator (dusg)
- vcadsr
- tzfm 3340 vco (currently being breadboarded0

Licence: CC-BY-SA 4.0
