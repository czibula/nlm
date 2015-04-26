# Frequently Asked Questions, Part 1 #

## What does the use of LED 3Wwhen at night you can see how a candle, regular diodes? ##
All LEDs, especially low-cost LEDs, have a specific time, which is quite short when working with a maximum current value.
Typical LEDs, have a luminance less than 1 lm.
Extra bright LED 5mm and 10mm super flux, have a luminance of 1.5 lm at 20 mA maximum current allowable.
3W LEDs cheap, have a luminance in the vicinity of 100-300 lm with a maximum permissible current of 700mA.<br>
Assuming the instantaneous value (for PWM) 100mA LED circuit, we get 1/7 the current limit value that is respectively around 28 lm, which gives a much better result in brightness.<br>
<br>
<h2>Can I use the LED luminance greater than 200lm without a heat sink?</h2>
Yes. There are already cheap 3W LED luminance 300-400lm that do not require the use of heat sink for use with NLM module.<br>
<br>
<h2>What is the power consumption of the module?</h2>
NLM2 module has a voltage stabilizer with a maximum current consumption of 100mA, but led only supplies and microprocessor control ATTiny44A SSU20 so here is negligibly small.<br>
In contrast, the total power consumption of the connected LED circuits depends on the method of software cycles of light and power diodes used in LED circuit <br>
For example, for 1 circuit collecting up to 100mA, controlled PWM to fill out the 25% and 2 50ms pulses / sec, mean current consumption by only 1/4 of the duration of the pulse / sec.<br>
Therefore, the current consumption should be calculated individually for lighting scheme used.<br>
<br>
<h2>Is it possible to change the 100R resistors?</h2>
Yes. Resistors easy it is to replace a new one. To calculate the desired value of the resistor, it is worth using the online calculator, keeping in mind that power on a continuous basis may not exceed 2W.<br>
<br>
<h2>Is it possible to control a relay?</h2>
Yes, if you use the relay of no more than 1W. Otherwise it will be necessary to choose a resistor in the LED circuit to a desired value, and may not be greater than 2W per circuit.<br>
For systems that do not require high current loads, eg. Camera shutter, for example, may want to use optocoupler such as CNY-17 with an additional resistor.<br>
<br>
<br>
<h2>Landing lights are activated inversely to the landing gear. How to set reverse programmatically?</h2>
If there is no source code with prefix revers_gear variable, usually is on the line as follows:<br>
<pre><code>led_gear = (durationS2 &lt; 1700)? true: false;</code></pre>
just change the sign to the opposite when compared to the value of:<br>
<pre><code>led_gear = (durationS2 &gt; 1700)? true: false;</code></pre>

<h2>ATTINY44 microprocessor has only 4 PWM outputs, where so many NLM2 module?</h2>
Truth. ATTiny44 has only 4 PWM outputs implemented "hardware" and for all outputs, PWM signal can be implemented in software. All inputs of the module can handle the PWM signal input.<br>
<br>
<h2>Why when I connect the tape led, weaker light module?</h2>
The module 100R1W resistors were used for each of the LED circuit.<br>
The tape has already led inside their circuits suitable resistor.<br>
It should therefore be thinking over whether to replace the resistor and LED strip module, the other a smaller resistance, or zero for the cable.<br>
Thus necessarily must then calculate that the total current consumption of the LED circuit, does not overload the power supply circuit in the module.<br>
<br>
<br>
<h2>How to choose the led power?</h2>
Datasheets LEDs indicate the parameters such as brightness and Instant light.<br>
In the case of the module of the PWM, should choose these diodes, which have the longest Instant light at the highest luminance level.<br>
This significantly reduces the consumption of electric power consumed by a circuit when we use the PWM value less filling while still maintaining a sufficient level of brightness of the LEDs.