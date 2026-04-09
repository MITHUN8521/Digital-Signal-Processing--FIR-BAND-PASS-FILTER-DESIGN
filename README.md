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
clc; % clear screen
clear all;
close all;

wc1 = input('enter the value of cut off frequency wc1: ');
wc2 = input('enter the value of cut off frequency wc2: ');
N = input('enter the value of filter: ');

alpha = (N-1)/2;
eps = 0.001;

% Band Pass Filter Coefficient
n = 0:1:N-1;

hd = (sin(wc2*(n-alpha+eps)) - sin(wc1*(n-alpha+eps))) ./ ((n-alpha+eps)*pi);

% center value
hd(alpha+1) = (wc2 - wc1)/pi;

% Hanning Window Sequence
wh = 0.5 - 0.5*cos((2*pi*n)/(N-1));

hn = hd .* wh;

% Plot
w = 0:0.01:pi;
h = freqz(hn,1,w);

plot(w/pi, abs(h), 'blue');
xlabel('Normalized Frequency');
ylabel('Magnitude');
title('Band Pass Filter using Hanning Window');
grid on;
```

## OUTPUT:
<img width="555" height="497" alt="Screenshot 2026-04-09 200954" src="https://github.com/user-attachments/assets/2dc8fdf0-4141-42b7-bd9f-6046bbbb2985" />

## RESULT:
![r5](https://github.com/user-attachments/assets/6b29e2dc-5f12-4a50-9a02-9953cdf4a847)

