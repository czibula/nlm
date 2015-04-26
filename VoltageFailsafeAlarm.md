# Voltage Failsafe Alarm #

how to easily prepare NLM2 module to trigger the alarm when the voltage drops.

Preparing undervoltage alarm should not be particularly difficult. You will need this connector, wires and resistors. I would recommend the whole place in a heat shrink tubing.

![http://i.imgur.com/f2gW5jZ.jpg](http://i.imgur.com/f2gW5jZ.jpg)

The resistors are selected by their own divider what we want. In the example I used resistors R-1 10kOhm and R-2 2kOhm. Resistors have their different tolerance, so be sure to measure the resistance of the actual values by typing in the code.

An application using an adapter for measuring voltage
http://i.imgur.com/G7YB79a_jpg


The code in your own program based on the examples for NLM2, you need to declare (enter below):

```

float volts = 0.0; // Volts
float voltsAlarm = 9.60; // min voltage alarm
float R1 = 10850.0; // 10k, resistance of R1 in Ohm
float R2 = 1988.0; // 2k, resistance of R2 in Ohm
const int referenceVolts = 5; // the default reference on a 5-volt NLM2.1 board  or 3.3 for NLM2.2
const int resistorFactor = (R2/(R1 + R2)); ```

However, in the for loop (), type the alarm service. In the example below, the lighting mode will be activated failsafe when the voltage is below the value specified by the variable voltsAlarm

```

volts = ((analogRead(input_Signal3) * referenceVolts) / 1024 ) / (resistorFactor);
if ( volts < voltsAlarm ) {
LEDS_Failsafe();
}```

The accuracy of measuring voltage depends mainly on the used resistors.