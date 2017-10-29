Please refer to textbook [chapter 10](https://github.com/cnchenpu/data-comm/blob/master/ppt/Ch10-Forouzan.ppt)

# Data-Link Layer Error Detection and Correction
- Error transmissions are caused by __Interference__, type of errors: <br>
![](fig/bit-error.png)
- To detect or correct errors, we need to send extra (__Redundant__) bits with data.
- __Error detection__
  - Looking only to see if any error has occurred
  - The answer is a simple yes or no.
- __Error correction__
  - Forward error correction
    - The process in which the receiver tries to guess the message by using redundant bits.
  - Retransmission
    - The receiver detects the occurrence of an error and asks the sender to resend the message.
- Redundancy is achieved through various __coding schemes__.
  - redundant bits: n > k
  ![](fig/coding-scheme.png)
  
  > EX: <br>
  > [4B/5B](https://github.com/cnchenpu/data-comm/blob/master/11_data-comm_digital-trans_D2D.md#4b5b) block coding <br>
  > 2<sup>4</sup> = 16 data-words <br>
  > 2<sup>5</sup> = 32 code-words <br>

## Error Detection
![](fig/error-detection-model.png)
An error-detecting code can detect only the types of errors for which it is designed; other types of errors may remain undetected.

## Error Correction
