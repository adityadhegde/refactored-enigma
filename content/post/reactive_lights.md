+++
title = 'Reactive Lights and where to find them'
date = 2024-08-21T10:47:27+05:30
draft = false
+++

# What I want to achieve
I am a man who enjoys the simple things in life, a giant computer monitor, and things like atmospheric lights which will react to 
the videos playing on the said monitor. 

Ofcourse I could buy something akin to that off the [internet](https://us.govee.com/products/govee-tv-backlight-3-lite?Size=For%2075-85%20inch%20TVs&Version=DUNE-themed%20Packaging), 
but this product was unavailable on [Amazon India](https://www.amazon.in). So with the exchange rate being what it is and 
the customs fees it would be would prohibitively expensive, and extremely tedious. So I decided to make one of my own.

Here's what the final product should look like, 	

<div style="display: flex; justify-content: center;">
<iframe width="235" height="424.5" src="https://www.youtube.com/embed/1Lx_C2iYTV0" title="Finding Nemo but the TV lights REACT! 🤯" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>

So ofcourse I spent the entire weekend obsessing over how can I make this happen, while making it as cost effective as possible.

## The plan

So roughly I need to do the following:

    1. Capture a screenshot of what's playing
    2. Analyse the image and turn it into colors which represent it
    3. Send it over to a micro controller which controls a LED strip

![Process_flow](/images/flow.svg)

This process needs to be repeated as often as possible to provide a seamless experience. . 

### What's required
With that said let's move on to what is needed to make this plan happen. I previously worked on building my 
own [mechanical keyboard](https://github.com/adityadhegde/shorty40) from scratch, which gave me some experience 
working with micro-controllers and [micropython](https://micropython.org/). So with some amount of internet sleuthing I was 
able to put together the following list

#### 1. Strip of 60 WS2812b controllable LED lights
These are compact three pin LEDs which are easy to power and used extensively in DIY projects making them widely supported.
 
#### 2. Xiao seediuno ESP32-C6 Micro-controller
ESP32 is a solid platform which has WiFi6 and Bluetooth connectivity, plenty of GPIO Pins, and micropython support. Xiao's Seediuno 
tiny form factor makes it an ideal choice given my limited desk space. It also boasts a USB-C input jack so it can be powered using 
a normal phone charger.

#### 3. A way to Decode what's on the screen
Just like all great things we start small here limiting ourselves to a single media player namely [VLC](https://www.videolan.org/vlc/). 
VLC has an in-built web API which allows complete control of the media player, including the ability to take screenshots. We can 
then easily read the screenshot from the disk and process it using python and send the processed data to the micro-controller 
over the WiFi connection.

## Hardware side of things
How to connect the lights to the micro controller
How to power the micro controller 

## How to communicate with the microcontroller over the Wifi
### Setting up the microcontroller with micropython
### Primer on controlling LEDs using micropython
### Connecting it to the wifi
### Setting up a server with takes a command using a get request 
[link to adafruit blog]
### Setting up power on and power off animation

## Calculating lights
### Setting up VLC
### Approach one [4 Quadrants method] 
#### Problems
### Approach two [Slats]
#### Calculating colors with weighted average
