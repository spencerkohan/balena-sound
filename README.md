This project is built on top of Balena Sound - the goal is to add a software crossover, so the raspberry pi acting as the sound server can output the bass and treble over separate channels.

This is achieved by adding [CamillaDSP](https://github.com/HEnquist/camilladsp) to the audio block to implement the crossover.

## Use Case

This software is built to power a 2-way bookshelf speaker, using a raspberry pi to stream audio over wifi and bluetooth.

Thanks to Balena-sound, it supports multi-room audio similar to a Sonos.

It is built with the following components:

## Speaker Drivers:
- A Dayton Audio TD20F-4 3/4" Soft-dome Neodynium Tweeter (4 Ohm)
- An ND105-8 4" Aluminum Cone Midpass Driver (8 Ohm)

## Hardware
- A Raspberry Pi 4 serves as the audio source
- A HiFiBerry Amp2 serves as the DAC and amp for the speaker drivers

It might be possible to run this project with a cheaper pi (i.e. pi zero) but I wanted to have plenty of headroom for prototyping.

## Enclosure
The speaker enclosure is built out of MDF with  baltic bearch plywood for the front panel.

The dimensions are:
- Width: Xmm
- Height: Xmm
- Depth: Xmm

# Modifications to Balena Sound

In order to achieve the software crossover, Camilla DSP is added to the balena-sound audio block.  This is the component responsible for handling audio streams and routing them to the hardware.

The following modifications have been made:

## 1. Install Camilla DSP

Camilla DSP has to be downloaded and installed.  The necessary steps have been added to `core/audio/Dockerfile.template`.
