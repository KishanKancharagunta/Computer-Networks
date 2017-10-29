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
![](fig/error-detection-model.png) <br>
EX:
As following code table
- If received __111__, there there is no valid code-word matched, so discard it.
- If received __000__, this is a vaild code-word in code table, the data-word is __00__.
- If sender sent __000__ but receiver received __011__ (2 bits corrupted), then it will not be detected and treat as data-word __01__.
- __An error-detecting code can detect only the types of errors for which it is designed; other types of errors may remain undetected.__

|Data-word|Code-word|
|:----:|:----:|
|00|000|
|01|011|
|10|101|
|11|110|

## Error Correction
EX: 
As following code table, sender sends __01011__ (__data-word: 01__) but receiver receives __01001__.
- Receiver finds the code-word is not in the code table, that means an error has occurred.
  - Assume there is only 1 bit corrupted.
  - Compare the received code-word with the code-words in the table.
  - Then find the code-word __01011__ in table has 1 bit that differ from the received code-word __01001__.
  - So correct the received code-word to __01001__, and consult the data-word is __01__.

|Data-word|Code-word|
|:----:|:----:|
|00|00000|
|01|01011|
|10|10101|
|11|11110|

