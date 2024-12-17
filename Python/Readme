We creat a python code exactly same as Matlab code to see the outputs.
here I will expalin what we code and what would we expect as outputs.

First of all we want to Define the Noise Transfer Function (NTF), variables using for this part of code are:
zeros: The locations of zeros for the NTF in the z-plane. Zeros represent frequencies where the transfer function becomes zero.
poles: The locations of poles for the NTF in the z-plane. Poles represent frequencies where the transfer function becomes infinite.
k: Gain factor for scaling the transfer function.
b, a: Coefficients of the numerator and denominator polynomials of the transfer function, respectively.
ntf: The discrete-time transfer function created using the TransferFunction class.

we Calculate RMS Gain of the NTF by:
OSR: Oversampling ratio. The higher the OSR, the narrower the noise bandwidth.
f_range: Frequency range from 0 to 0.5/OSR,which corresponds to the noise bandwidth of the modulator.
z_range: Complex points on the unit circle corresponding to f_range (used to evaluate the NTF).
H_eval: Evaluates the transfer function H(Z) at the points in z_range.
rms_gain: Root mean square (RMS) gain of the NTF within the noise bandwidth.
sigma_H: The RMS gain expressed in decibels.
              
Bode Plot: Magnitude and Phase Response 
frequencies: A range of normalized frequencies from 0 to 0.5 (Nyquist frequency).
z_bode: Complex points on the unit circle corresponding to the frequency range.
H_bode: Evaluates the NTF at the points in z_bode.
magnitude: The magnitude of H(z) in decibels.
phase: The phase of H(z) in degrees.

Pole-Zero Plot Variables:
z: Locations of zeros of the NTF in the z-plane.
p: Locations of poles of the NTF in the z-plane.
k: Gain of the transfer function (unchanged here).
This step plots the zeros and poles in the complex plane to visualize the NTF structure.

Simulate the Delta-Sigma Modulator Variables:
N: Total number of samples (simulation length).
f_in: Frequency of the input sine wave (determined by the OSR).
n: Time indices for the input signal.
input_signal: A sine wave with frequency f_in and amplitude 0.5.

Variables:
v: The quantized output signal of the delta-sigma modulator.
x: State variables representing the integrator outputs.
The loop simulates the behavior of a second-order delta-sigma modulator:
First integrator (x[0]): Integrates the input signal minus the quantized feedback.
Second integrator (x[1]): Further accumulates the first integrator’s output minus the quantized feedback.

Spectral AnalysisVariables:
spectrum: The FFT of the modulator output 
v, scaled by a Hanning window to reduce spectral leakage.
frequencies: Corresponding frequency values for the FFT result.

signal_bin: The FFT bin corresponding to the input signal frequency 𝑓in.
noise_bins: All other bins (excluding the signal bin) up to half the Nyquist frequency.
signal_power: Power of the signal at 𝑓in.
noise_power: Total power in the noise bins.
snr: Signal-to-noise ratio in dB.

SINC Filter Design and Application
sinc_filter: A low-pass filter designed using the sinc function to suppress out-of-band noise.
filtered_output: The modulator output v filtered through the SINC filter.
