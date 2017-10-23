Please refer to textbook [chapter 4](https://github.com/cnchenpu/data-comm/blob/master/ppt/Ch4-Forouzan.ppt).

# Analog to Digital Conversion
## PCM (Pulse Code Modulation)
- 1. The analog signal is sampled.
- 2. The sampled signal is quantized.
- 3. The quantized values are encoded as streams of bits. <br>
![](fig/PCM.png)

### Sampling
- The analog signal is sampled every T<sub>s</sub> seconds, where T<sub>s</sub> is the sample interval or period. The inverse of the sampling interval is called the sampling rate or sampling frequency and denoted by f<sub>s</sub>, where f<sub>s</sub> = 1/T<sub>s</sub>. <br>
![](fig/PCM-sampling.png) <br>
- According to the __Nyquist theorem__, the sampling rate must be at least 2 times the highest frequency contained in the signal. <br>
![](fig/Nyquist-rate.png)

### Quantization
- approximate the value of the sample amplitude to the quantized values
  - approximate creates qunatization error
- normalized value = actual amplitude / delta
  - delta = (V<sub>max</sub> - V<sub>min</sub>) / Levels <br>
![](fig/PCM-quantization.png)
  
# Transmission Modes  
![](fig/trans-mode.png)
- Parallel transmission: send bits together
- Serial transmission: send bits one-by-one
  - needs parallel/serial converter
- Asynchronous transmission: use gap (start and end bits) between sending data
- Synchronous transmission: no gaps between sending data
