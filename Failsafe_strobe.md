#failsafe

# Strobe lights #

For short-term switching of lights for LED circuits selected, you can use the analogWrite. Conversely, if you want to further strengthen the strobe effect only for short-term use, no more than 50ms, you can use digitalWrite.

Be sure to use a strobe with LED 3W, gives a very strong visual impact.

## Code ##

If you do not use the selected LED circuits, remove the appropriate line, the control circuit selected, or use the # symbol.
```

/* Turn Off the lights */
void LEDS_OFF() {
analogWrite(led_12, LEDOFF);
analogWrite(led_34, LEDOFF);
analogWrite(led_56, LEDOFF);
analogWrite(led_78, LEDOFF);
analogWrite(led_09, LEDOFF);
analogWrite(led_10, LEDOFF);
}

/* Turn On the lights */
void LEDS_ON() {
analogWrite(led_12, LEDBLINK);
analogWrite(led_34, LEDBLINK);
analogWrite(led_56, LEDBLINK);
analogWrite(led_78, LEDBLINK);
analogWrite(led_09, LEDBLINK);
analogWrite(led_10, LEDBLINK);
}

/* All lights flashing - eg failsafe mode */
void LEDS_Failsafe() {
LEDS_ON();
delay(50);
LEDS_OFF();
delay(40);
LEDS_ON();
delay(50);
LEDS_OFF();
delay(40);
LEDS_ON();
delay(50);
LEDS_OFF();
}```