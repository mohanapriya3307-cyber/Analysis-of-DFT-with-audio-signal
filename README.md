# EXP 1 :  ANALYSIS OF DFT WITH AUDIO SIGNAL

# AIM: 

  To analyze audio signal by removing unwanted frequency. 

# APPARATUS REQUIRED: 
   
   PC installed with SCILAB/Python. 

# PROGRAM: 
// Clear environment
clear;
clc;
close;

// Sampling parameters
Fs = 8000;                  // Sampling frequency in Hz
T = 1 / Fs;                 // Sampling period
L = 2048;                   // Length of signal (number of samples)
t = (0:L-1) * T;            // Time vector

// Generate test audio signal: sine wave at 440 Hz (A4 note)
f_signal = 440;             // Frequency of signal in Hz
x = 0.7 * sin(2 * %pi * f_signal * t);

// Plot time-domain audio signal
figure(1);
plot(t, x);
xtitle('Audio Signal in Time Domain', 'Time (seconds)', 'Amplitude');
xgrid();

// Compute DFT using FFT
X = fft(x);

// Compute two-sided spectrum P2 and single-sided spectrum P1
P2 = abs(X / L);
P1 = P2(1:L/2+1);
P1(2:$-1) = 2 * P1(2:$-1);

// Frequency vector for single-sided spectrum
f = Fs * (0:(L/2)) / L;

// Plot frequency spectrum (magnitude)
figure(2);
plot(f, P1);
xtitle('Single-Sided Amplitude Spectrum of Audio Signal', 'Frequency (Hz)', 'Magnitude');
xgrid();


// analyze audio signal

# OUTPUT: 

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/203c0511-1245-4cf1-9ab3-0e8ccdbecfd7" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/a8226390-5483-4ef3-b2ed-07daea7927df" />

# RESULTS
To analyze audio signal by removing unwanted frequency is sucessfully completed.
