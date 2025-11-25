# Design-of-FIR-Filters-using-hanning-window

#DESIGN OF FIR DIGITAL FILTER 

# AIM: 
          
  To generate design of low pass FIR digital filter using SCILAB 

# APPARATUS REQUIRED: 

  PC Installed with SCILAB 

# PROGRAM 
clear;
close;

M = 51;              // Filter length
fc = 0.4;            // Normalized cutoff frequency (0 to 0.5)

// Create Hanning window
n = 0:M-1;
w = 0.5 - 0.5 * cos(2 * %pi * n / (M-1));

// Ideal impulse response for Low Pass Filter
hd = sin(2 * %pi * fc * (n - (M-1)/2)) ./ (n - (M-1)/2);
hd((M-1)/2 + 1) = 2 * %pi * fc;  // fix center value

// Apply window
h = hd .* w;

// Normalize filter coefficients
h = h / sum(h);

// Display coefficients
disp(h);

// Plot impulse response
subplot(2,1,1);
plot(h);
xlabel('Samples');
ylabel('Amplitude');
title('Impulse Response of Low Pass FIR Filter using Hanning Window');

// Frequency response
[H, f] = frmag(h, 512);
subplot(2,1,2);
plot(f, H);
xlabel('Normalized Frequency');
ylabel('Magnitude');
title('Frequency Response of Low Pass FIR Filter');

# OUTPUT
![WhatsApp Image 2025-11-25 at 16 19 08_58c40490](https://github.com/user-attachments/assets/7e0dfb4e-004e-4914-b24b-856713d6f263)


# RESULT
Thus , generate design of low pass FIR digital filter using SCILAB are verified.
