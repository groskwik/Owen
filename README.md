# Factors for one-sided tolerance limits (aka Owen k-factors)

For use with HP 50G or HP 49G+ Calculator

February 9, 2019

## Abstract
Let's assume that X is a random variable with a normal distribution.
The probability is gamma that at least a proportion P of X is below m + k*s.
Where m is an estimate of the mean and s is an estimate of the variance (from
a sample of X).

gamma is also known as the confidence level.

## Reference
Factors for one-sided tolerance limits:
https://www.nrc.gov/docs/ML1403/ML14031A495.pdf

NIST/SEMATECH e-Handbook of Statistical Methods
https://www.itl.nist.gov/div898/handbook/prc/section2/prc263.htm

## Credits
Thanks to University of Texas and their Source Code CDFLIB90:
https://biostatistics.mdanderson.org/SoftwareDownload/SingleSoftware.aspx?Software_Id=21

Thanks to Egan Ford for his HPGCC guide:
http://sense.net/~egan/hpgcc/

And of course thanks to the HPGCC team!

## Installation

### Install the ARM toolbox library

First Install the ARM toolbox library (which is needed to run ARM code)
https://www.hpcalc.org/details/6090

1. Copy the file ARMToolbox/SETUP.BIN to your HP 50g.
2. On the HP 50g put the number 2 on the stack:

![ARM](http://sense.net/~egan/hpgcc/pics/armtool1.gif "ARM Toolbox 1")

3. put SETUP.BIN on the stack, not 'SETUP.BIN'.  Your 50g should look like this:

![ARM](http://sense.net/~egan/hpgcc/pics/armtool2.gif "ARM Toolbox 2")

Now press ![ARM](http://sense.net/~egan/hpgcc/pics/botton_eval.gif "ARM Toolbox 2") , then ![ARM](http://sense.net/~egan/hpgcc/pics/botton_on.gif "ARM Toolbox b") +.
![ARM](http://sense.net/~egan/hpgcc/pics/button_f3.gif"ARM Toolbox 3") 

4. Verify that the ARM Toolbox is installed by pressing ![ARM](http://sense.net/~egan/hpgcc/pics/button_right.gif "ARM Toolbox r) ![ARM](http://sense.net/~egan/hpgcc/pics/button_two.gif "ARM Toolbox 2") ![ARM](http://sense.net/~egan/hpgcc/pics/soft_armto.gif "ARM Toolbox soft")

### Install the code

1. Put the directory EXTEND at the root of your SD card.
2. Install the Owen Library, Owen.lib in the port of your choice.

The Owen library consist of one single program "Owen"

## Example
An engineer is doing 50 measurements of the thickness of a component. The mean value is 2.3 mm and the
standard deviation is 0.2 mm.

What is the 0.95/0.95 k-factor ?

In the calculator enter:
n: 50
P: 0.95
Gamma: 0.95

The calculator gives the following result:
k = 2.064993399768

This means that there is a probability of 95% that 95% of the component's
thickness is less than 2.3+k*0.2 = 2.713 mm.

This value can be checked with the tables given in the reference pdf, page 47
(page 49 of the file): k = 2.065.

This can also be checked with R, using tolerance package (normtol function)
https://cran.r-project.org/web/packages/tolerance/
