# Sensor Fusion Radar Project
Eugene Klitenik

## FMCW Waveform Design
Slope of the chirp is calculated using the formulas described in the lecutres and matches the expected value of 2e13.

## Simulation loop
Initial value of target is set at 100m and the 1D FFT correctly results in the estimate.

##Range FFT (1st FFT)
Initial value of target is set at 100m and the 1D FFT correctly results in the estimate.

## 2D CFAR
The 2D CFAR processing is correctly be able to suppress the noise and separate
the target signal. The output appears to match that provided in the walkthrough.

## Implementation steps for the 2D CFAR process.
CFAR is implemented by determining the average noise in the areas near the target (both in range and doppler), and then using this noise as a base for threhsolding. An offset is added to the base noise value do to specify the SNR (i.e. how much higher the signal should be above the noise to result in a detection.)

## Selection of Training, Guard cells and offset.
Training and guard cells are selected in order to provide a reasonable estimate of average conditions. In this implementation 10 training cells are used in range and doppler dimensions, and 4 guard cells are used in each dimension. An offset of 10 is added to the average noise level to ensure that only detections that are significantly higher than the noise are captured. 

## Steps taken to suppress the non-thresholded cells at the edges.
Non-thresholded cells at the edges don't get evaluated and are therefore set to 0.