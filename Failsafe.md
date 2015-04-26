#failsafe

# Failsafe #

Failsafe NLMs used for switching lights, alarm buzzer, or a parachute.

## Enabling Failsafe ##

Failsafe mode can be activated automatically or on request from the transmitter :
  * Loss of signal in the receiver,
  * [Power supply voltage drop below a preset threshold](https://code.google.com/p/nlm/wiki/VoltageFailsafeAlarm),
  * [The temperature rise of a sensor](https://code.google.com/p/nlm/wiki/Failsafe_temperature),
  * Or at the request from the transmitter.

Each mode Failsafe, requires a different way of NLM controller software.

## Actions ##

For each of the fail-safe mode, you can assign the appropriate operation mode. Are possible to obtain:
  * [Light switch strobe mode](https://code.google.com/p/nlm/wiki/Failsafe_strobe),
  * [Inclusion of audible signals](https://code.google.com/p/nlm/wiki/Failsafe_buzzer),
  * [Release the parachute](https://code.google.com/p/nlm/wiki/Failsafe_parachute),
  * Engine cut-off,
  * Set the servos in a predetermined position.

.