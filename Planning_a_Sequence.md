#Planning a Sequence.

# Planning a Sequence #

_Pilot on board. Engines Off._ <br>
<img src='http://i.imgur.com/L7v3OAV.jpg' />

<i>Stop with the engines running.</i> <br>
<img src='http://i.imgur.com/n3t1THl.jpg' />

<i>The flight with the engine off. Waiting on the runway.</i> <br>
<img src='http://i.imgur.com/BgE9XGF.jpg' />

<i>Normal flight mode. Navigating the taxiway. Engine On</i> <br>
<img src='http://i.imgur.com/xChcPHJ.jpg' />

Sample code for the example above.<br>
<pre><code><br>
/* Mode 2 with beacon and landing lights */<br>
void LEDS_Mode2() {<br>
if (led_gear !=false) {<br>
analogWrite(led_09, LEDBLINK);<br>
} else {<br>
analogWrite(led_09, LEDOFF);<br>
}<br>
analogWrite(led_34, LEDBLINK);<br>
analogWrite(led_78, LEDBLINK);<br>
delay(50);<br>
analogWrite(led_34, LEDOFF);<br>
analogWrite(led_78, LEDOFF);<br>
delay(50);<br>
// 100 ms<br>
analogWrite(led_12, LEDBLINK);<br>
analogWrite(led_78, LEDBLINK);<br>
delay(50);<br>
analogWrite(led_12, LEDOFF);<br>
analogWrite(led_78, LEDOFF);<br>
delay(50);<br>
// 200 ms<br>
analogWrite(led_12, LEDBLINK);<br>
analogWrite(led_78, LEDBLINK);<br>
delay(50);<br>
analogWrite(led_12, LEDOFF);<br>
analogWrite(led_78, LEDON);<br>
delay(50);<br>
// 300 ms<br>
analogWrite(led_12, LEDBLINK);<br>
delay(50);<br>
analogWrite(led_12, LEDON);<br>
delay(50);<br>
// 400 ms<br>
if (led_beacon !=false) analogWrite(led_56, LEDBLINK);<br>
delay(50);<br>
analogWrite(led_56, LEDOFF);<br>
delay(50);<br>
// 500 ms<br>
if (led_beacon !=false) analogWrite(led_56, LEDBLINK);<br>
delay(50);<br>
analogWrite(led_56, LEDOFF);<br>
delay(50);<br>
// 600 ms<br>
if (led_beacon !=false) analogWrite(led_56, LEDBLINK);<br>
delay(50);<br>
analogWrite(led_56, LEDOFF);<br>
delay(350);<br>
// 1000 ms<br>
} </code></pre>