#failsafe

# Temperature Failsafe #

## Overview ##

Sometimes it happens that immediate action is needed if the temperature is exceeded. Can be connected to the module, low-cost temperature sensor.
In the illustrated example, a temperature sensor used LM35 / TMP35. You can also use any of the similar parameters.

## Connecting to a Temperature Sensor ##

![http://i.imgur.com/47Di7ZX.jpg](http://i.imgur.com/47Di7ZX.jpg)  ![http://i.imgur.com/GNpmIZT.jpg](http://i.imgur.com/GNpmIZT.jpg)   ![http://i.imgur.com/F22Hu3E.jpg](http://i.imgur.com/F22Hu3E.jpg)

## Reading the Analog Temperature Data ##

To convert the voltage to temperature, simply use the basic formula:
Temperature in °C = (Vout in mV) / 10

For NLM 2.1 with internal supply 5V<br>
<pre><code>Voltage at voltage_input_Signal3 = durationS3 * ( 5000 / 1024 )</code></pre>
This formula converts the number 0-1023 from the input_Signal3 into 0-5V<br>
<br>
For NLM 2.2 with internal supply 3.3V<br>
<pre><code>Voltage at voltage_input_Signal3 = input_Signal3 * ( 3300 / 1024 )</code></pre>
This formula converts the number 0-1023 from the input_Signal3 into 3.3V<br>
<br>
To convert the voltage value at the temperature, use the following formula:<br>
<pre><code><br>
# read voltage and convert to temperature<br>
durationS3 = analogRead(input_Signal3);<br>
voltage_input_Signal3 = durationS3 * ( 5000 / 1024 )<br>
float temperature = (voltage_input_Signal3 - 0.5) * 100 ;<br>
<br>
# actions<br>
float temperature_critical = 45.0;<br>
if ( temperature &gt; temperature_critical ) {<br>
# put here your code<br>
}</code></pre>