#videoswitch
# Video Switch #

The module can be used with a switch video sources.<br>
Making the switch is easy and cheap.<br>
Switching cameras, done by select switch from the transmitter.<br>

The sample application.<br>
<br>
<img src='http://i.imgur.com/tE3umtR.jpg' />

<h1>Sample source code</h1>

If you are based on the source code contained in the trunk, replace the following:<br>
<pre><code><br>
// CONN 4, Wejście sygnału S4<br>
//  dodatkowe złącze We/Wy<br>
byte input_Signal4 = 10; // PIN 2<br>
<br>
// CONN 5, Wejście sygnału S5<br>
//  dodatkowe złącze We/Wy<br>
byte input_Signal5 = 9; // PIN 3</code></pre>

with code<br>
<pre><code><br>
byte output_Signal4 = 10; // PIN 2<br>
byte output_Signal5 = 9;  // PIN 3</code></pre>

In function <i>setup()</i> add the following code<br>
<pre><code><br>
pinMode(output_Signal4, OUTPUT);<br>
pinMode(output_Signal5, OUTPUT);<br>
digitalWrite(output_Signal4, LOW);<br>
digitalWrite(output_Signal5, LOW);</code></pre>

In function <i>loop()</i> add the following code<br>
<pre><code>  duration = pulseIn(input_Signal3, HIGH);<br>
if (duration &lt; 1601) {<br>
digitalWrite(output_Signal5, LOW);<br>
digitalWrite(output_Signal4, HIGH);<br>
} else if (duration &gt;1600){<br>
digitalWrite(output_Signal4, LOW);<br>
digitalWrite(output_Signal5, HIGH);<br>
}<br>
</code></pre>


Remember, the connector CONN-4 and CONN-5, do not have GND. You need to use a different connector cable to connect the GND, or solder the cable directly.<br>
<br>
Scheme of the video switch.<br>
<img src='http://i.imgur.com/ld0X5pP.png' />    <img src='http://i.imgur.com/jLL8uoz.png' />

Required parts:<br>
1x ILD206 or similar<br>
2x 1k resistor<br>
1x pcb<br>
5x 2x1 connector<br>