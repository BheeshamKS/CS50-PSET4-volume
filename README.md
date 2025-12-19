# CS50 PROBLEM SET 4 - Volume

This repository contains my solution for the Volume problem from Harvard's CS50 Problem Set 4. The program modifies the volume of a `.wav` audio file by scaling each audio sample by a given factor.

## Files

`volume.c` : Main solution file that reads a WAV file, adjusts its volume, and writes the modified audio to a new file.

## Description

The program takes three command-line arguments:

- Input WAV file
- Output WAV file
- Volume scaling factor (floating-point number)

It performs the following steps:

- Validates command-line arguments
- Opens the input and output files
- Copies the 44-byte WAV header unchanged
- Reads each 16-bit audio sample from the input file
- Multiplies each sample by the given factor
- Writes the modified sample to the output file
- Closes both files safely

This ensures the output file remains a valid WAV file while its volume is increased or decreased.

## Output Behavior

- A factor greater than `1.0` increases the volume
- A factor between `0.0 and 1.0` decreases the volume
- A factor of `1.0` leaves the audio unchanged

## Example Run
```bash
./volume input.wav output.wav 2.0
```

This doubles the volume of `input.wav` and saves the result as `output.wav`.

## How to Run

Compile and run using GCC:

```bash
gcc -o volume volume.c
./volume input.wav output.wav factor
```


Replace `factor` with a floating-point number representing the volume scale.
