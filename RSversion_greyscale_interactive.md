# Version: Greyscale Interactive - Radiosilence
This version of the Radiosilence project introduces direct interactivity through live audioviisual thresholds, shifting the system from passive observation to conditional visibility.
Rather than consistently mapping all sound, this setup reacts selectively, revealing or concealing visual information (real time by volume or pitch) depending on the soundscape of the room.
This version reinforces the idea of sensitivity and presence of self as presence of sound in the audioscape. 

There are two subtypes to this version: 
ST 1: Live video 
ST 2: Image 

both subtypes can use either Volume (dB) or pitch (Hz) as measurement (for values, see below)

Please note that this version only fulfills its aim when practiced live. 

---

## Concept 

Instead of a grid, this version uses live video footage/pre-taken still-footage as its visual base.

A microphone picks up live ambient sound. A screen or projection surface then displays either:
- a hidden/revealed image / live video
- greyscale (functions as visibility threshold)
- with a 0,5second average measurement of dB/Hz the model reacts accordingly. 

### Scale/Mapped Range

The greyscale values should corespond as follows

for Volume: 
89dB and up = #000000
38-43dB = image
0dB = #FFFFFF 
between 0 and 89dB, greyscale is mapped in descending greys in 10dB ranges, except the exact values of 38-43dB(being the usual "perfect" talking volume) (e.g.: 0-9 = FFFFFF, 10-19 = EAEAEA, (...), 80-89 = 151515, 90+ = 000000)

for Frequency: 
120Hz and up = #000000
50-60Hz = image
20Hz and below = #FFFFFF
intermediate frequencies mapped proportionally in descending greys as done for volume 

---
## Spatial & Technical Setup

- Microphone (live AudioIn)
  - positioned near center of space to capture ambient dynamic better. (directional mic preferred to avoid external triggers)
- running program (see 'Visual logic' below)
- Screen/beamer + projection surface
- ( for ST 1: camera (live VideoIn))

---

# Subtype 1 
live video

**Measurement/Input**: Average volume (in decibels, dB)
**Visual Logic**: 
The live video stream remains hidden (black) unless the volume/frequency remains between **38-43dB**/**50-60Hz**, which is roughly the range of soft conversation or rather quiet backround presence/the range of spoken vowels and voiced consonants.
Only within this window of volume does the actual image appear. If the room is too loud, the screan fades to black, if the room is too quiet the screen fades to white.

# Subtype 2 
still image
This subtype works almost identical to ST 1, except it doesn't rely on live video. The measurements and general Logic remain the same, but at "perfect volume/pitch" instead of live-video an image shows up. (The image itself remains undefined in this instruction, as the version has not been trialed. see 'Notes' for more). 

---

## Notes
This version introduces access control through acoustic behaviour, allowing each individual/group to understand their impact on the soundscape.The room becomes a performative field of silence, tone and awareness.  
The intended outcome would make an indivdual/a group of visitors hum into the room to keep a certain volume/frequency in order to see the visual footage, therefore directly creating a constant "noise" and needing to understand the sensitivity of information being lost to too much/too few ambient sound. 
  
