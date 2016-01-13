# Non-inverting amplifier

Basic non-inverting amplifier circuit with 2 resistors producing gain of:
```
 G = (r1 + r2) / r1
```

For an audio amplifier it is required to achieve a fixed gain across audible 
frequencies (and a bit more).
This will be defined as the range `10Hz - 20KHz`.

The op amp being used is a 741 (or a model of).

By varying the values of `r1` & `r2` the Gain and Bandwidth of the the amplifier
can be varied.
As the gain increases, the bandwidth decreases.

## Instructions

Run the circuit with:
```ngspice op_amp.cir```

For the sake modelling, test over input frequency range 10Hz - 100KHz (just
wider than normal human hearing).

Apply a 1v ac supply of increasing frequency to `Vin`:
```
ac dec 10 10Hz 100KHz
```
* note: the second argument (in this case `10`) is points per decade *

The output is on point 2. Plot this with:
```
plot v(2)
```

## Results

1.
Arbitrary resister choices to start
```
r1 = 1.2KOhm
r2 = 4.7KOhm
Expected Gain = 4.917
Gain at 20Khz = 4.877
```
Bandwidth is acceptable on the range specified.
[Plot 1](plots/plot_1.png)

2.
Increasing gain by increasing r2
```
r1 = 1.2KOhm
r2 = 9.1KOhm
Expected Gain = 8.583
Gain at 20KHz = 8.380
```
Gain increased without affecting bandwidth of range of interest.
[Plot 2](plots/plot_2.png)

3.

Pushing the gain.
```
r1 = 1.2KOhm
r2 = 43KOhm
Expected Gain = 36.83
Gain at 20Khz = 25.5
```
Gain at this level is much high but drops off at a higher rate. A gain this high
wouldn't be suitable.


## Findings

As expected the increasing the value of r2 increases the gain, however the
bandwidth of the circuit decreases.
[Plot 3](plots/plot_3.png)
