+++
title = 'Reactive Lights and where to find them'
date = 2024-08-21T10:47:27+05:30
draft = false
+++

# What I want to achieve
I am a man who enjoys the simple things in life, a giant computer monitor, and things like atmospheric lights which will react to 
the videos playing on the said monitor. Ofcourse I could buy something akin to that off the [internet](https://us.govee.com/products/govee-tv-backlight-3-lite?Size=For%2075-85%20inch%20TVs&Version=DUNE-themed%20Packaging).

With the going exchange rate and the customs fees it would be would prohibitively expensive, and extremely boring. 
So I decided to make some of my own.

Here's what the final product should look like, 	

<iframe width="478" height="849" src="https://www.youtube.com/embed/1Lx_C2iYTV0" title="Finding Nemo but the TV lights REACT! 🤯" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

So ofcourse I spent the next entire weekend obsessing over how can I make this happen, while making it as cheap as possible.

## What's required
1. lights ws2812b
2. Microcontroller
3. A way to communicate to the microcontroller
4. A way to Decode what's on the screen

## Hardware side of things 
How to connect the lights to the micro controller
How to power the micro controller 

## How to communicate with the microcontroller over the Wifi
### Setting up the microcontroller with micropython
### Primer on controlling LEDs using micropython
### Connecting it to the wifi
### Setting up a server with takes a command using a get request 
[link to adafruit blog]
### Setting up power on and power off animation ]

## Calculating lights
### Setting up VLC
### Approach one [4 Quadrants method] 
#### Problems
### Approach two [Slats]
#### Calculating colors with weighted average
