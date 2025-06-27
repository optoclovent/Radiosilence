# Version: Morse Code Audio - Radiosilence

This is the "original" concept that seeded the whole project. The idea: environmental noise becomes signal. 
By picking up ambient conversations and transforming them into Morse-code, the space itself becomes a noisy feedback loop, where people indirectly generate their own interference. 

## Concept 
A microphone placed in a public indoor setting (e.g., hallway, cafeteria, or else) listens in. The ambient sound is: 
1. transcribed into **text** using live speech-to-text software (initial trials used **Vosk**, note: use the Vosk model according to the language that will most possibly be spoken in the environment in which the model is run),
2. Translated into **Morse code** via script (see below),
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

The following script pieces have been my attempts at coding into/for TD, that have eihter errored or not responded at all. 

a) to use Vosk with Python:
-> the printed result must be saved as txt output

import vosk # Load the Vosk model 
model = vosk.Model("voskSmallFr") 

recognizer = vosk.KaldiRecognizer(model, 16000) 

audio_file = "speech3.wav" 

    while True: 
        # Read a chunk of the audio file 
        data = audio.read(4000) if len(data) == 0: 
            break 
        # Recognize the speech in the chunk 
        recognizer.AcceptWaveform(data) 

result = recognizer.FinalResult() 
print(result)


b) for 'Morse_converter.py' 
-> is supposed to translate the text from a) into morse and save that result as txt again

def text_to_morse(text):
    morse = []
    for char in text.upper():
        if char in MORSE_CODE_DICT:
            morse.append(MORSE_CODE_DICT[char])
        else:
            continue
    return ' '.join(morse)

def main():
    try:
        with open('output_speech.txt', 'r', encoding='utf-8') as infile:
            input_text = infile.read()
    except FileNotFoundError:
        print("File 'output_speech.txt' not found.")
        return

    morse_code = text_to_morse(input_text)

    with open('output_morse.txt', 'w', encoding='utf-8') as outfile:
        outfile.write(morse_code)

    print("Conversion complete. Morse code saved to 'output_morse.txt'.")


c) Intended for Touchdesigner as Minimal loader for DAT Execute or Text DAT

def load_morse_to_dat(dat):
    morse_file_path = project.folder + "/output_morse.txt"

    try:
        with open(morse_file_path, "r", encoding="utf-8") as file:
            morse_text = file.read().strip()
    except Exception as e:
        morse_text = f"Error: {str(e)}"

    print("Morse code loaded:")
    print(morse_text)

    if op('morse_data'):
        op('morse_data').clear()
        op('morse_data').appendRow([morse_text])
    else:
        print("Warning: 'morse_data' DAT not found")

    return

load_morse_to_dat(op('null1'))
