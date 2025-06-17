# Version: Greyscale Visual - Radiosilence 

This version shifts the project's trajective further away from language and instead becomes a representation of sensitive echo, visualizing dynamics of sound we often ignore (see notes for implications and outlook)
Instead of translating words to Morse code, it listens, measuring the **presence of sound** in space and translating it into shades.

For this approach there are two subtypes: 
ST 1: Volume-based greyscale (dB)
ST 2: Frequency-based greyscale (Hz)

---

## Concept 

This version keeps the 16x16 grid format from 'RSversion_morse_visual.md' (filled row by row from top left to bottom right), but instead of Morse characters, **each cell reflexts one sound measurement**.
Every 0.5 seconds the system takes a reading (dB or Hz depending on ST) and assigns a corresponding greyscale value.
After 128 seconds the grid is full, resulting in a 256-cell map. 
Similar zu the morse visual model this can be practiced live or non-live.

#### in short: 
- Grid: 16x16 = 256 cells
- Time window: 0.5s per cell = 128 seconds for full grid
- Each 0.5s: take measurement, translated into greyscale value
- Once grid is full (see "Modes"

## Modes
### Live Mode:
- Grid fills in real-time
- After 256 measurements it overwrites itself, creating a looped visual pulse

### Non-Live
- Field recordings or spatial sound excerpts are used
- Grid fills once, then stops
- Output is saved/exported (to print/exhibit as static piece)

---

## Spatial & Technical Setup
### Live Setup
a) Microphone distant from the output screen to avoid feedback/self-trigger
b) Microphone installed in front of output screen (encouraged interaction)
c) Microphone placed in a separate room from output screen (abstract link)

### Non-Live Setup
System can be relocated and restarted to capture different locations (same when working with pre-recorded samples)
-> allows a **series of images** as a sort of map/metric

---

# Subtype 1

- **Measurement/Input**: Average volume (in decibels, dB)
- **Scale/Mapped Range**:
  - 0 dB (near silence) -> '#FFFFFF' (white)
  - 89 dB (potentially damaging) -> '#000000' (black)
  - in 10 dB ranges mapped in descending greys (F.i.: 0-9 = FFFFFF, 10-19 = EAEAEA, (...), 80-89 = 151515, 90+ = 000000)
  
---

# Subtype 2 

- **Measurement/Input**: Average pitch/fundamental frequency (in Hertz, Hz)
- **Scale/Mapped Range**:
  - 12-24Hz -> '#FFFFFF'
  - 108-120Hz -> '#000000'
  - intermediate frequencies mapped proportionally in descending greys

---

## Notes

If this version is looked at as artistic research it could use the sensitivity of the microphone as a variable to (for instance) track how much more dominant male talkers are (term "male" here: typically lower pitched, typically louder) and thus shine a light on gender as an indicative of appropriation of public space when speaking.
This approach would need equal parts of unaware "participants". 
