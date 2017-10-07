# Digital Signal
- Use digital bits (0/1) to encode voltage levels.
- N levels need log<sub>2</sub>N bits.

![](fig/digital-signal.png)

- based on __Fourier analysis__, a digital signal is a composite analog signal, which the bandwidth is infinite.
  - __Fourier__ showed that a composite periodic signal can be decomposited into a serial of sine and cosine functions which called ___Fourier series___. 
  - A digital signal composited by infinite number of frequency of signals, so its bandwidth is infinite.
  - a horizon line in the time domain, no changes in time, means a frequency of 0.
  - a vertical line in the time domain means a frequency of infinity.
- most digital signals are ___nonperiodic___, so __periodic__ and __frequency__ are not appropriate characteristics.
- __Bit rate__ is the number of bits in 1 second (bps).
  > EX: <br>
  > HDTV - 1920x1080 pixels a picture, 24 bits colors per pixcel, and 30 frames per second. <br>
  > The bit rate is 1920 x 1080 x 30 x 24 &asymp; 1.5 Gbps
- __Bit interval__ is the inverse of the bit rate (second).
  > EX: <br>
  > A signal has a bit rate of 2000 bps, its bit interval is <br>
  > 1/2000s = 0.0005s = 500 &mu;s <br>
  ![](fig/bit-interval.png)
- __Bit length__ is the distance one bit occupies on the transmission medium. (The concept of __wavelength__ in analog signals)
- A digital signal is a composite analog signal with an infinite bandwidth.

## Transmission of Digital Signals
![](http://2.bp.blogspot.com/-eTPsW40tID0/UaRHWMH8BbI/AAAAAAAAIws/SiT59SYIZH4/s1600/difference+between+Baseband+and+BroadBand.gif)
- __Baseband Transmission (without modulation)__
  - __Low-pass__ channel has bandwidth with frequencies between 0 and f.
  - signal that has a very narrow and near-zero frequency range
- __Broadband Transmission (using modulation)__
  - __Band-pass__ channel has bandwidth with frequencies between f1 and f2.
