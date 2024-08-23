+++
title = 'Reactive Lights and where to find them. Part 1 of 2'
date = 2024-08-21T10:47:27+05:30
draft = true
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

So ofcourse I spent the entire weekend obsessing over how can I make this happen, 
while making it as cost effective as possible.

Here's what my version looks like.

![placeholder](#)

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
 
#### 2. Xiao Seeed Studio ESP32-C6 Micro-controller
ESP32 is a solid platform which has WiFi6 and Bluetooth connectivity, plenty of GPIO Pins, and micropython support. Xiao Seeed 
studio's tiny form factor makes it an ideal choice given my limited desk space. It also boasts a USB-C input jack so it can be powered using 
a mobile phone charger.

#### 3. A way to Decode what's on the screen
Just like all great things we start small here limiting ourselves to a single media player namely [VLC](https://www.videolan.org/vlc/). 
VLC has an in-built web API which allows complete control of the media player, including the ability to take screenshots. We can 
then easily read the screenshot from the disk and process it using python and send the processed data to the micro-controller 
over the WiFi connection.

## Hardware side of things
This part turned out to be more straight forward than I expected, barring the bits which required some soldering
it was much like putting together lego blocks. 

### Step 1. Setup the LED strip

![A single LED from the Strip](/images/LED.jpeg)
<p style="text-align: center;"><em>A single LED from the strip</em></p>

As mentioned earlier the WS2812b has three pins, the 5volt power pin, a Data Input(Din) pin, and a ground(Gnd) pin. I used 
jumper cables given the micro-controller and the LED strip would be put together using a breadboard.

Here's what the soldered LED will look like

![Soldered LED](/images/LED_soldered.jpeg)
<p style="text-align: center;"><em>Soldered LED</em></p>

### Step 2. Attaching the LED strip to the micro-controller

The easy part is putting all this together, all it takes is a couple of jumper cables and a breadboard.

![Pinout](/images/Pinout.png)
<p style="text-align: center;"><em>Micro-controller Pinout</em></p>

The power pin on the LED strip takes an input of 5volts, which we connect to the 5V output pin 
on the micro-controller, similary the ground pin on the LED strip connects to the ground pin of the 
micro-controller. The "Din" data input pin on the micro-controller connects to any of the 
general purpose IO pins labels from D0 to D10 on the micro-controller. Make a note of which data pin 
you use.

![Assembled Breadboard](/images/assemby.jpeg)
<p style="text-align: center;"><em>Assembled Breadboard</em></p>

**Note:** If you are using a larger number of lights running on full brightness you should consider 
powering the LED strip using an external power source to ensure you don't fry your micro-controller.

## Closing thoughts
This post takes us through the hardware setup. In the next one I discuss the software implementation.

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
