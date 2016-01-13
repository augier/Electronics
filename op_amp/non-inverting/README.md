# Non-inverting amplifier

Basic non-inverting amplifier circuit with 2 resistors producing gain of:
```
 G = (r1 + r2) / r1
```

For an audio amplifier it is required to achieve a fixed gain across audible frequencies (and a bit more).
This will be defined as the range `10Hz - 20KHz`.

The op amp being used is a 741 (or a model of).

By varying the values of `r1` & `r2` the Gain and Bandwidth of the the amplifier can be varied.
As the gain increases, the bandwidth decreases.

## Instructions

Run the circuit with:
 ```ngspice op_amp.cir```

For the sake of my interests, testing over frequency range 10Hz - 20KHz (just wider than normal human hearing).

Apply a 1v ac supply of increasing frequency to `Vin`:
```
ac dec 10 10Hz 20KHz
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
Bandwidth = 2KHz
```
Band width is an order of magnitude too small.
[Plot 1](plots/plot_1.png)

2.
Decreasing r2
```
r1 = 1.2KOhm
r2 = 2KOhm
Expected Gain = 2.667
Bandwidth = 2KHz
```
Expecting the bandwidth to have increased but it has stayed the same.
[Plot 2](plots/plot_2.png)