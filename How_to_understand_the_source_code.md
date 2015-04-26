# How to understand the source code #

## Comments ##
Comments are preceded by a description, as well as placed at the end of the line to which they relate.
The text between the characters ```
/*``` and ```
*/```, as well as text prefixed with ```
//``` means a comment.

## Fixed values ##
Begin with the prefix indicates the type of value.

The values for brightness in relation to the value of the PWM.
Three solid, determine how light will be emitted to the output circuit LEDs.
The NLM-1 applies to all outputs, for NLM-2 applies only to go out LED1-8.
The values of these constants can be changed to customize their own preferences.
You can also extend the source code with the following values of what you require.
```

const byte LEDOFF   = 0;
const byte LEDON    = 32;
const byte LEDBLINK = 192;
```
Typical values for these constants are in the range of 0 to 255.<br>
<a href='https://code.google.com/p/nlm/wiki/PWM_with_NLM'>Here you will find information on using the values for these constants, on the effect that you get in the output circuit.</a>
<br>

<h2>Variable values</h2>
Output module circuits correspond to the respective outputs of the microprocessor.<br>
In the source code, are marked with the prefix <pre><code>led_nn</code></pre>
where <i>nn</i> corresponds to the numbers marked on the module outputs as LED-<i>nn</i>.<br>
<br>
Input circuitry of the module correspond to the respective inputs of the microprocessor,<br>
are marked with the prefix <pre><code>input_Signal n</code></pre> where <i>n</i> is the number of connections for the module respectively CONN-<i>n</i>.<br>
<br>
<h2>Functions</h2>
The source code is divided into functional blocks, carrying out certain tasks.<br>
Block source code, marked feature is preceded by the prefix "void" which is a string indicating the name of the Function. The function code is placed between the braces "{}".<br>
<br>
For the Arduino environment, the necessary functions that must be present in the code, it<br>
<pre><code><br>
void setup () {}<br>
void loop () {}</code></pre>
For NLMs, the most common functions are:<br>
<pre><code><br>
void LEDS_OFF () {}<br>
void LEDS_ON () {}<br>
void LEDS_Failsafe () {}<br>
void LEDS_Mode1 () {}<br>
void LEDS_Mode2 () {}</code></pre>

If your RC model requires more lighting modes, use the syntax of what has been proposed above.<br>
For example, you want to have a mode 3 and 4, write the source code of the function names, respectively:<br>
<pre><code><br>
void LEDS_Mode3 () {}<br>
void LEDS_Mode4 () {}</code></pre>

<h2>Operation of signals at the inputs of the module</h2>

The input signals are interpreted by the code. Most often it will use the internal functions of the Arduino environment:<br>
<pre><code><br>
pulseIn ()<br>
digitalRead ()<br>
analogRead ()</code></pre>
Typically, PPM-PWM signal from the receiver RC, these values are from 900 to 2200, therefore, the source code must be used to read the value of <i>int</i> or <i>unsigned long</i>.<br>
<br>
In the source code NLM find the most relevant variables for reading the value of individual inputs:<br>
<pre><code><br>
unsigned long durationS1;<br>
unsigned long durationS2;<br>
unsigned long durationS3;<br>
unsigned long durationS4;<br>
unsigned long durationS5;</code></pre>


<h2>More about programming in the Arduino IDE</h2>

More about how to program source code, please visit the project <a href='http://arduino.cc/en/Reference/HomePage'>Arduino.</a>