## Carrier Acquistion
FPGA based doppler shift corrector block for a satellite telemetry receiver chain.

## Why is it needed?
Monitoring a satellite's telemetry data is key to ensuring the health, status and functionality of on-board systems throughout its mission lifecycle. 

Due to a satellite's high orbital velocities the carrier frequency offset due to the doppler effect is usually of the order of few hundred KHz which can make the demodulator go 
out of lock especially for costas loop demodulators having loop bandwidth in the 100s or 1000s of Hz to correct this massive offset a coarse frequency compensator is present in 
the receiver chain before the matched filter and demodulator.

## How does it work?
By squaring the signal and computing the FFT, we get a peak at the centre of the signal spectrum. By finding the index of the peak, it is then multiplied with the frequency resolution
to obtain the frequency offset. This frequency offset is then fed into a NCO which is mixed with the original signal to correct for the doppler shift

## Block Diagram
<img width="908" height="232" alt="image" src="https://github.com/user-attachments/assets/a0603f23-aa73-45d6-bf51-e87a187c2df8" />

