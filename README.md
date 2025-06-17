# Radiosilence

**Radiosilence** is a conceptual project exploring how *sound* - particularly live, environmental sound - acts and functions as an interactive variable in open spaces. It aims to challenge how we perceive, transform and react to audio as data by experimenting with its representation as code, image or distortion.

The core idea lies in *listening* to ones surroundings and translating that into another signal (either visual or auditory). 

This repository serves as the documentation and blueprint for multiple approaches. 

## Directive 
This project aims to: 
- use live microphone input (Audio In) as a dynamic control or generative source
- Reinterpret AudioIn-Information as either:
  - Auditory transformation (e.g., sound into morse code tones)
  - Visual abstraction (e.g., image rendering based on loudness or frequency)
- Propose alternative modes of engagement with sounds in public or interactive environments

Though the project is currently theoretical, the following files outline the different **possible realisations**

## System Requirements (conceptual)
Each version of this project requires: 
| Component | Description |
|-----------|--------------|
| Microphone | Captures environmental sound |
| Application | Real-time processing (TouchDesigner, vvvv, Max/MSP etc.) |
| Output | Either speakers or screens, depending on version (for Image Output: live rendering or still image) | 

--

## Project Versions 

Please note that all provided files are descriptive. The only included code (if existing) will be failed trials.

| File Name | Description |
|-----------|-------------|
| 'RSversion_morse_audio.md' | Translates Speach-to-Text-to-Morse into AudioOut |
| 'RSversion_morse_visual.md' | Converts Morse from Speach-to-Text-to-Morse into a visual |
| 'RSversion_greyscale_visual.md' | Builds a grid of greyscae values based on sound intensity over time |
| 'RSversion_greyscale_interactive.md' | Interactive piece: an image is revealed/hidden depending on volume/frequency |

--

## Contribution
If you are a developer, artist, or technologist interested in collaborating on one or more of these prototypes, feel free to: 
- open an issue to discuss details
- Fork the repo and contribute a functional patch
- translate any of the markdown versions into working code
- use existing contributions to realise any of the projects versions in a program of your choice

## License

This project is shared for educational and collaborative purposes
