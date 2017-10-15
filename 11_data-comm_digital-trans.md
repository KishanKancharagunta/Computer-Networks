Please refer to textbook [chapter 4](https://github.com/cnchenpu/data-comm/blob/master/ppt/Ch4-Forouzan.ppt).

# Digital to Digital Conversion

## Data vs. Signal Element
- Data element: a bit that represent a piece of information.
- Signal element: the shortest unit of a digital signal.
- data elements per signal elements: __r = data elements / signal elements__

![](fig/data-signal-element.png)

- Data rate (N): the number of data elements (bits) send in one second __(bps)__.
- Signal rate (S): the number of signal elements send in one second __(baud)__.
- Signal rate also called _pulse rate_, _modulation rate_ or _baud rate_.
> Signal rate __S = N/r__ <br>
> or in average __S = c x N x 1/r__ <br>
> where __c__ is the case factor.

## The baud rate (not the bit rate) determines the required bandwidth for a digital signal.
- So the minimum bandwidth is signal rate: __B<sub>min</sub> = c x N x 1/r__
- The [Nyquist sample rate](https://github.com/cnchenpu/data-comm/blob/master/08_data-comm_channel.md#noiseless-channel) shows the maximum data rate of a channel is __N<sub>max</sub> = 2 x B x log<sub>2</sub>L__.
> - A signal with L levels actually can carry log<sub>2</sub>L bits per level, <br>
> - if each level corresponds to 1 single element, and in average case (c = 1/2). <br>
> Then: <br>
> __N<sub>max</sub> = 1/c x B x 1/r = 2 x B x log<sub>2</sub>L__


