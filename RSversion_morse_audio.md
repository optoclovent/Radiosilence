# Version: Morse Code Audio - Radiosilence

This is the "original" concept that seeded the whole project. The idea: environmental noise becomes signal. 
By picking up ambient conversations and transforming them into Morse-code, the space itself becomes a noisy feedback loop, where people indirectly generate their own interference. 

## Concept 
A microphone placed in a public indoor setting (e.g., hallway, cafeteria, or else) listens in. The ambient sound is: 
1. transcribed into **text** using live speech-to-text software (initial trials used **Vosk**),
2. Translated into **Morse code** via script,
3. Read aloud using **assigned sound cues** for dots and dashes (e.g., high-pitched blip for a dor, lower-pitched buzz for dash. the exact sound does not matter, as long as it is distinguishable and tending towards "unpleasant")

Result: as people talk, the system plays morse-code-echoes of their conversations. The more they talk, the more noise, the more distorted the speech-to-text-info gets. If conversations stop, so does the echo.
The speech-to-text layer sin't meant to work "well". Its imperfections feed the distortion, as misheard words/phrases, unheard words/phrases and errors create some sort of ghost text that only resembles the happening speech and turns it into an alien signal.

---
## Spatial & Technical Setup
- **Microphone placement**:
   - Should be central enough to pick up a good range of ambient sound
   - Should avoid catching the AudioOut signal directly - either by:
     - Placing seaker and mic far apart
     - Using directional mics / sensitivity thresholds
     - Building in an "ignore" timer (note: issue in TouchDesigner with auddio being cut prematurely)
     - Physically separating mic & speaker into different rooms

- **Output**:
  - Audio playback of Morse translation (no visual output)
  - Sound should be slightly unpleasant or attention drawing, but distinguishable (see Concept > 3.)

---
## Notes
> first trials were made in **TouchDesigner**, but issues emerged:
- **Python scripting** was difficult to integrate with the audio chain
- **Vosk** (for speach to text) could not be implemented directly
- external scripts caused errors, failed to run, or had no effect.

Due to my limited coding background, these were exploratory rather than final builds. However, anyone interested in picking up the idea and realizing it in any environment is warmly invited to do so. (see below for script trials)

## Closing Thoughts
This version is less about information delivery and more about sonic atmosphere:
> a passive listener becomes a noisy mirror of the human environment.

---
### script trials 
