# Digital-Signal-Processing--FIR-BAND-PASS-FILTER-DESIGN
## AIM:
To generate design of Band Pass FIR digital filter using Window.
## Software Required:
MAT LAB R2012.
## Algorithm:
Step 1: Open MATLAB and Write the program.

Step 2: Read the values of cut off frequency wc.

Step 2: Read the values of Order of the filter N.

Step 3: Find out the desired impulse response of the Band Pass filter Coefficient.

Step 4: Find out the windowing sequence.

Step 5: Plot the magnitude spectrum with x-label and y-label with suitable title.

Step 6: Terminate the program.

## PROGRAM: 
```
clc;                
clear all;
close all;

wc1 = input('Enter the lower cut off frequency: ');
wc2 = input('Enter the upper cut off frequency: ');
N   = input('Enter the value of filter length: ');

alpha = (N-1)/2;
eps   = 0.001;

% Band Pass Filter Coefficient
n  = 0:1:N-1;
hd = (sin(wc2*(n-alpha+eps)) - sin(wc1*(n-alpha+eps))) ./ (pi*(n-alpha+eps));

% Blackman Window Sequence
wb = 0.42 - 0.5*cos((2*pi*n)/(N-1)) + 0.08*cos((4*pi*n)/(N-1));

% Final Band Pass Filter
hn = hd .* wb;

% Frequency Response
w = 0:0.01:pi;
h = freqz(hn,1,w);

% Plot
plot(w/pi, abs(h), 'ms');
xlabel('Normalized Frequency');
ylabel('Magnitude');
title('Band Pass Filter using Blackman Window');
grid on;
```

## OUTPUT:
<img width="689" height="557" alt="image" src="https://github.com/user-attachments/assets/80bfb727-888f-452c-82a4-d3d06ee32008" />


## RESULT:
![WhatsApp Image 2026-04-09 at 10 41 31](https://github.com/user-attachments/assets/6a904b60-dab8-46c4-b5f8-c5a2882ba68f)

