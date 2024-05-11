# LabView LED sequence
## About
This is an assignment work for my Automatisation II subject.
### Problem
Create a light game with Mitsubishi FX PLC according to the following operation:

Pressing the S1 push button should move the outputs (Y0-Y5, a total of 6) from left to right, so that the first output Y0 is immediately active, the next output Y1 for 2.5 seconds, the following outputs for 2, 1.5, 1 second, respectively, and the last one for 0.5 seconds compared to the previous one. The operation should be continuous until the S3 push button is pressed.
Pressing the S2 push button should continuously move the outputs from left to right, alternating between even and odd outputs every second. It should be possible to stop it at any time with S3.
Prevent simultaneous use of S1 and S2 to avoid abnormal operation (only one push button should be valid at a time, and a neutral state is required for switching).
Mode switching should only be possible in the neutral state.

### Solution
I created 6 round LED lights, 3 buttons and 2 state structures, wrapped in a while loop which has the STOP button as breaker.
Inside the state structures encased, there are flat sequences with the local variables of the LEDs paired with a timer.

On S1 or S2 activation, the program disables the other button while it's operating.

One flaw is that when STOP is pressed, the sequence doesn't stop immediately, instead, becouse of the case structure acts like a loop itself, it only comes to stop, when the sequence got to a full iteration.

### Grafcet
![Diagram](https://github.com/fulopbencus/LabView-LED-sequence/blob/main/grafcet.png)

## Requirements
LabVIEW installed:
Feature Usage Your system must meet the following minimum requirements to run and use LabVIEW. Processor Windows: Pentium 4M (or equivalent) or later (32-bit) Pentium 4 G1 (or equivalent) or later (64-bit) Linux: Pentium 4 G1 (or equivalent) or later RAM Windows: 1 GB Linux: 1 GB

## License
GPL-2.0-or-later

## Author
Fülöp Bence <fulopbencus@gmail.com>
