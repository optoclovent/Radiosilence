# Version: Morse Code Visual - Radiosilence

This version translates live or recorded speech (or speech resembling sounds) into **Morse-code visuals**.
Instead of audio playback, Morse characters are displayed in a 16x16 grid - one character per cell.

---

## Concept
A microphone captures ambient sound & speech.
The sound is: 
1. Converted into **text** via speech-to-text software (e.g., **Vosk**)
2. Translated into **Morse code** (dots and dashes)
3. Mapped visually into a **16x16 grid**
  - Left to right, row by row; one cell = one Morse unit
    
When the grid is full, the system ends the intake process, resulting in a visual record of sound/speech.

---

## Variants & Modes of Operation
### Live Mode
- The grid begins empty; behaves like a loop
- As new Morse characters arrive, they are placed one by one (see above)
- After 256 Units the grid begins **overwriting from the beginning**
Visuals update in real time.

### Non-Live Mode
Use the same software chain with pre-recorded samples from various locations/situations (see notes below)
- The grid is filled once (per sample run) and remains unchanged; System runs until the grid is full, then **stops intake**
The results are supposed to be **saved/exported** as an image and printed or archived

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

## Morse Output
the following translation of single characters to morse can be copied as base for the ‘output_morse.txt’ when coding the converter. 

MORSE_CODE_DICT = {
    'A': '.-', 'B': '-...', 'C': '-.-.', 'D': '-..', 'E': '.', 
    'F': '..-.', 'G': '--.', 'H': '....', 'I': '..', 'J': '.---', 
    'K': '-.-', 'L': '.-..', 'M': '--', 'N': '-.', 'O': '---', 
    'P': '.--.', 'Q': '--.-', 'R': '.-.', 'S': '...', 'T': '-', 
    'U': '..-', 'V': '...-', 'W': '.--', 'X': '-..-', 'Y': '-.--', 
    'Z': '--..',
    '0': '-----', '1': '.----', '2': '..---', '3': '...--', 
    '4': '....-', '5': '.....', '6': '-....', '7': '--...', 
    '8': '---..', '9': '----.',
    ' ': '/' 
}

---

## Notes
This version was not tested beyond theory. 

cf. 'Non-Live Mode': If the setup is relocated, this would allow the results to work as artistic research, mapping either a string of locations or a single location in different situations
