# -Frequency-Modulation-and-Demodulation-using-NumPy-and-Matplotlib-

__Aim:__

To implement and analyze frequency modulation (FM) using Python's NumPy and Matplotlib libraries.

__Apparatus Required:__ 

1. Software: Python with NumPy and Matplotlib libraries
   
2. Hardware: Personal Computer

 
__Theory:__

Frequency Modulation (FM) is a method of transmitting information over a carrier wave by varying its 
frequency in accordance with the amplitude of the input signal (message signal). The frequency of the carrier 
wave is varied according to the instantaneous amplitude of the message signal.

__Algorithm:__

1. Initialize Parameters: Set the values for carrier frequency, message frequency, sampling frequency, and 
   frequency deviation.
   
2. Generate Time Axis: Create a time vector for the signal duration.
    
3. Generate Message Signal: Define the message signal as a cosine wave.
    
4. Compute the Integral of the Message Signal: Calculate the integral of the message signal over time.
    
5. Generate FM Signal: Apply the FM modulation formula to obtain the modulated signal.
 
6. Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signal.

__Programme:__
```c
# FM USING PYTHON


import numpy as np
import matplotlib.pyplot as plt

Am = 32.6
fm = 570
Ac = 16.3
fc = 5700
fs = 90000
t = np.arange(0, 3/fm, 1/fs)
m = Am * np.cos(2 * 3.14 * fm * t)
plt.subplot(3,1,1)
plt.plot(t, m)
plt.title("Message Signal")
plt.xlabel("Time")
plt.ylabel("Amplitude")
c = Ac * np.cos(2 * 3.14 * fc * t)
plt.subplot(3,1,2)
plt.plot(t, c)
plt.title("Carrier Signal")
plt.xlabel("Time")
plt.ylabel("Amplitude")
df = 2000
beta = df / fm
print("Modulation Index (β) =", beta)
s = Ac * np.cos(2 * 3.14 * fc * t + beta * np.sin(2 * 3.14 * fm * t))
plt.subplot(3,1,3)
plt.plot(t, s)
plt.title("Frequency Modulated Signal")
plt.xlabel("Time")
plt.ylabel("Amplitude")
plt.tight_layout()
plt.show()

```

__Tabulation:__

![WhatsApp Image 2025-11-20 at 21 24 55_52ac8eb6](https://github.com/user-attachments/assets/dfc2f2f5-a824-4edd-b6ed-b59b30ba2bfc)


__Output:__

<img width="630" height="469" alt="download (1)" src="https://github.com/user-attachments/assets/ec6da3a7-6417-47b2-ba07-37c7d71d4189" />


__Result:__

The message signal, carrier signal, and frequency modulated (FM) signal will be displayed in separate plots. The modulated signal will show frequency variations corresponding to the amplitude of the message signal.
