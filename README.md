# THIS PROBABLY WON'T WORK YET
So keep that in mind if you wanted to use it. I'm currently testing it using a Teensy 3.2 running custom code but I only need to change the wiper resistance for my current project so other features may not work.

# AD5292
Arduino library for the Analog Devices AD5292 with I2C interface.
The AD5272 is 1024-position (12 bits).
There are 20 kΩ, 50 kΩ, 100 kΩ nominal resistance versions.
This library supports both 8- and 10- bit versions.

## AD5292 Key Features
 - I2C Interface. including 400 kHz fast mode
 - address input with three possible values for three sub-addresses in I2C space
 - reset input
 - 20-times programmable wiper memory (you don't have to us this), which restores to the programmed value on reset.
 - if you have not used the 20-TP memory, reset loads a midscale value
 - single or dual supply operation for unipolar or bipolar applications
 - unlimited setting lifetime via I2C interface
 - same code can work on both resolution devices, the two lsb are ignored on the 8-bit device

## How and Why We Use It
 - set point for a programmable current sink used to precisely drive a laser or LED, it is an input to the opamp which drives a FET
 - we could have used a DAC but this device has a programmable setpoint which does not require configuration once set.
 - because it is a resistor, you can place it in a circuit with resistors 'above' and 'below' it, arranged such that you can put its effective range within a desired window of values, not just 0 to full scale. For us, in this application, this was useful and easier than using a DAC.

### Comments
 - This was forked from https://github.com/systronix/Systronix_AD5274 and made to work with the AD5292
 - See the source code for plenty of explanatory comments
 - The 20-TP memory is a bit unconventional, see the data sheet and code for comments and examples

### TODO
 - Pretty much everything.
 - Update control codes
