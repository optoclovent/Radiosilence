# Version: Sound Interactive Installation - Radiosilence 

This version of *Radiosilence* translates ambient sound into physical motion and noise using a 16x16 grod-like-net with paper elements.
The system converts recorded or live audio data into mechanical impulses, resulting in a spatial sound sculpture. 

---
## Concept 
In a room, a net of 16x16 knots is installed horizontally. From each knot down hangs a thread that holds a piece of paper at its end (the paper pieces need to be proportional to the net-size (diameter of holes) in order to be able to come into contact.) The paper pieces are supposed to be randombly folded, crumpled or otherwise shaped, as it acts as a embodiment and as a passive resonator.
Depending on the chosen size of the net: either every 4th knot (larger net) or every 8th (smaller net) in both directions is connected (upwards) to a small acutator or motor via thread, allowing response. 

## Mapping 
- Grid Size: 16 x 16 (256 nodes, 25 or 9 motorized points)
- Acurator Grouping: Motors are triggered based on volume range thresholds.
  The thresholds (in decibels) are as follows: (read from top left to bottom right, row by row, *numbers for the 9-motor-option*)
  *89* and up, 85.8, *82.6*, 79.4, *76.2*, 73, 69.8, 66.6, 63.4, 60.2, *57*, 53.8, *50.6*, 47.4, *44.2*, 41, 37.8, 34.6, 31.4, 28.2, 25, *21.8*, 18.6, *15.4*, 12.2, *9* and below

  Each motor responds to their range threshold being triggered by sampled volume, whether responding live or non-live (recordings) sound.
  The motors are supposed to "tug" at the net, thus a rotating motion from the motor would be seinsible, one rotation per trigger.

---
## Spatial & Technical Setup 
- Net Structure: any net works, only needs to be suspended in a way that stretches it enough so it doesn't hang relaxed.
- Paper Elements: Uniform size proportional to diameter of net-holes, variably formed (folded, crumpled, otherwise shaped), attached to nylon/other thread strings with needle, tied to the nodes of the net
- Motors: 25 or 9 lightweight acutators, distributed evenly either 4x4 intervals or 8x8 intervals
- Control System:
  - Microcontrollor or TouchDesigner/Arduiono combination
  - Volume detection via Microphone AudioIn or WAV analysis
  - Mapping algorithm distributes motor pulses based on amplitude

### mode options
#### Live Mode:
Audio via live microphone input, responding directly to ambient sound scape 

#### Non-Live Mode: 
Beforehand processed recordings of ambient sound/noise that should be mapped through installation 

---
## Output
The moving net creates collisions between the paper elements, which generates a subtle noise like rustling or crackling, which is similar in sound to both static or other background nose, as well as leaves in trees and wind.

## Notes
The rustling from the installation becomes a mimic to the ambient rather than being a monument or a lesson; it emerges as a sort of system artifact.
