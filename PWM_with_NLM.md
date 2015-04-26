#PWM with NLM

# Introduction #

When planning a lighting sequence, choose a LEDON and LEDBLINK parameters in the code.
The recommended value for the variable LEDON is 16-32, while the variable LEDBLINK suggested value is 128-192.

Inside the module 1.4, all LED outputs are outputs for the PWM.
Module 2.1 connector only PWM outputs are 1-8.

Increasing the duty cycle leads to increased power consumption.


# LEDON values ​​for the PWM. #

## 16 ##

![http://i.imgur.com/eYKvD5M.png](http://i.imgur.com/eYKvD5M.png)

## 32 ##

![http://i.imgur.com/DTkbmt4.png](http://i.imgur.com/DTkbmt4.png)

## 64 ##

![http://i.imgur.com/GEb1yJF.png](http://i.imgur.com/GEb1yJF.png)

## 128 ##

![http://i.imgur.com/GFADWe9.png](http://i.imgur.com/GFADWe9.png)

## 192 ##

![http://i.imgur.com/G8nFFMj.png](http://i.imgur.com/G8nFFMj.png)

# Arduino #

More on PWM Arduino, you will [find here](http://arduino.cc/en/Tutorial/PWM)