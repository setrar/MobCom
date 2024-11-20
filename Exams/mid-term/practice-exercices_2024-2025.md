| Mobile Communication Techniques |
|:-:|
| Practice Questions MOBCOM |
| Fall 2024-2025 |
| Petros Elia, elia@eurecom.fr | 

1) Starting from encoding bits at the transmitter, label the communication process up to decoding bits
at the receiver (in other words, start with bits, then baseband-discrete, ... de-modulation, ...)

Here’s the communication process in a compact form:

1. **Source Bits** →  
2. **Channel Encoding** →  
3. **Bit-to-Symbol Mapping** →  
4. **Baseband Signal (Pulse Shaping)** →  
5. **Frequency Upconversion** →  
6. **Channel Transmission** →  
7. **Frequency Downconversion** →  
8. **Matched Filtering** →  
9. **Sampling** →  
10. **Symbol Detection** →  
11. **Channel Decoding** →  
12. **Decoded Bits**.

2) Describe a reason why are we mostly interested in the discrete baseband representation of channel
rather than the actual continuous analog form


We focus on the discrete baseband representation because it simplifies analysis and processing by reducing complexity, enabling efficient digital signal processing (DSP) techniques, while preserving all the essential information of the analog signal within the Nyquist sampling rate.

3) Describe the probability density function of a real Gaussian random variable $\mathcal{N}(0, 1)$


The PDF of $ \mathcal{N}(0, 1) $ is:  
$
f_X(x) = \frac{1}{\sqrt{2\pi}} e^{-\frac{x^2}{2}}, \quad x \in \mathbb{R}.
$  
It is symmetric about 0, peaks at $ x = 0 $, and decays exponentially.

4) Describe the probability density function of a complex n-dimensional Gaussian random vector
(uncorrelated)

For a complex $ n $-dimensional Gaussian random vector $ \mathbf{z} \sim \mathcal{CN}(0, \sigma^2 \mathbf{I}) $ with uncorrelated components, the probability density function (PDF) is:

$
f_{\mathbf{z}}(\mathbf{z}) = \frac{1}{(\pi \sigma^2)^n} e^{-\frac{1}{\sigma^2} \|\mathbf{z}\|^2},
$

where $ \mathbf{z} \in \mathbb{C}^n $, $ \sigma^2 $ is the variance per component, and $ \|\mathbf{z}\|^2 $ is the squared magnitude of the vector.

5) Describe the probability density function of a complex n-dimensional Gaussian random vector
(uncorrelated)




6) Give an approximation of the tail of a Gaussian random variable $\mathcal{N}(0, \mathcal{N}_0/2)$


For a Gaussian random variable $ X \sim \mathcal{N}(0, \mathcal{N}_0/2) $, the **tail probability** for large $ x > 0 $ can be approximated as:

$
P(X > x) \approx \frac{\sqrt{\mathcal{N}_0/2}}{\sqrt{2\pi} x} e^{-\frac{x^2}{\mathcal{N}_0}},
$

where the exponential term dominates for large $ x $, and the prefactor provides a correction for the tail decay.

7) What is the projection of a vector $\underline{u}$ onto a space $V$ spanned by $\{v_i\}_i$?


The projection of a vector $ \underline{u} $ onto the space $ V $ spanned by $ \{ \underline{v}_i \}_i $ is:

$
\text{Proj}_V(\underline{u}) = \sum_i \frac{\langle \underline{u}, \underline{v}_i \rangle}{\langle \underline{v}_i, \underline{v}_i \rangle} \underline{v}_i,
$

assuming $ \{ \underline{v}_i \} $ are linearly independent.

8) Describe in words the meaning of , coherence bandwidth $W_c$ , coherence time $T_c$ , delay spread $T_d$ , Doppler spread $D_s$


- **Coherence Bandwidth ($W_c$)**: The frequency range over which the channel's frequency response is approximately constant. Indicates the channel's ability to preserve signals across frequencies.

- **Coherence Time ($T_c$)**: The time duration over which the channel's time-varying characteristics remain stable. Reflects the rate of channel variation.

- **Delay Spread ($T_d$)**: The time difference between the arrival of the earliest and latest significant multipath components. Determines the level of time dispersion.

- **Doppler Spread ($D_s$)**: The range of frequency shifts caused by relative motion between the transmitter, receiver, and scatterers. Indicates the extent of spectral broadening.

9) Relate the above $W_c$, $T_c$, $T_d$, $D_s$ to each other

The relationships between $ W_c $, $ T_c $, $ T_d $, and $ D_s $ are based on reciprocity in time and frequency domains:

1. **Coherence Bandwidth ($W_c$) and Delay Spread ($T_d$)**:
   $
   W_c \approx \frac{1}{T_d}.
   $
   A large $T_d$ (significant multipath) leads to a smaller $W_c$ (narrower frequency range where the channel is flat).

2. **Coherence Time ($T_c$) and Doppler Spread ($D_s$)**:
   $
   T_c \approx \frac{1}{D_s}.
   $
   A high $D_s$ (rapid relative motion) leads to a smaller $T_c$ (shorter time during which the channel is stable).

These relationships highlight the inverse proportionality between coherence metrics and the corresponding spread metrics.

10) What is the probability of error (w.r.t to **SNR**) in **AWGN** channels


The probability of error in an AWGN channel is:

1. **BPSK**:  $
P_e = Q\left(\sqrt{2 \cdot \text{SNR}}\right).
$

2. **M-PSK (approx.)**:  $
P_e \approx 2 \cdot Q\left(\sqrt{2 \cdot \text{SNR} \cdot \sin^2\left(\frac{\pi}{M}\right)}\right).
$

3. **M-QAM (approx.)**:  $
P_e \approx \frac{4}{\log_2(M)} Q\left(\sqrt{\frac{3 \cdot \text{SNR}}{M-1}}\right).
$ 

Error decreases exponentially with increasing SNR.

11) Describe the standard **AWGN** detection problem of two signals $\pm a$ in $\mathcal{N}(0, \mathcal{N}_0/2)$ noise.


The **AWGN detection problem** for signals $ \pm a $ in $ \mathcal{N}(0, \mathcal{N}_0/2) $ noise involves:

- **Received signal**: $ y = s + n $, where $ s \in \{+a, -a\} $ and $ n \sim \mathcal{N}(0, \mathcal{N}_0/2) $.
- **Decision Rule**:  $
  \text{Decide } +a \text{ if } y > 0, \text{ and } -a \text{ if } y < 0.
  $
- **Probability of Error**:  $
  P_e = Q\left(\sqrt{\frac{2a^2}{\mathcal{N}_0}}\right),
  $
where $ Q(x) $ is the Q-function.

12) What is the main difference in communications in **AWGN** channels v.s. fading channels


In **AWGN channels**, the signal is affected only by constant additive Gaussian noise, with performance depending on SNR. In **fading channels**, the signal experiences both noise and random amplitude/phase variations due to multipath, requiring techniques like diversity and equalization to combat time-varying impairments.

13) Write the channel model for fading channels? Do it for **SISO** and then for **MIMO**, including
dimensions.


### **Channel Model for Fading Channels**

- **SISO**:  
  $
  y = h x + n,
  $
  where $ h \in \mathbb{C} $, $ x \in \mathbb{C} $, $ n \sim \mathcal{CN}(0, \mathcal{N}_0) $, and $ y \in \mathbb{C} $.

- **MIMO**:  
  $
  \mathbf{y} = \mathbf{H} \mathbf{x} + \mathbf{n},
  $
  where $ \mathbf{H} \in \mathbb{C}^{M \times N} $, $ \mathbf{x} \in \mathbb{C}^{N \times 1} $, $ \mathbf{n} \sim \mathcal{CN}(0, \mathcal{N}_0 \mathbf{I}) $, and $ \mathbf{y} \in \mathbb{C}^{M \times 1} $.

14) What is the main cause of (fast) channel variations in time?


Fast channel variations are primarily caused by **relative motion** between the transmitter, receiver, and scatterers, leading to **Doppler effect** and time-varying **multipath fading**.

15) When can a channel be considered fast fading and when slow fading?


- **Fast Fading**: $ T_c < T_s $ (channel varies within a symbol).  
- **Slow Fading**: $ T_c > T_s $ (channel constant over multiple symbols).

16) What is the main cause of error in fading channels?


The main cause of error in fading channels is **deep fades**, which reduce the signal-to-noise ratio (SNR) due to destructive multipath interference.

17) Describe the concept of degrees of freedom.


The **degrees of freedom (DoF)** represent the number of independent signal dimensions available for communication, determined by time, frequency, or spatial resources. For MIMO, DoF is $ \min(M, N) $; for time-frequency, it is approximately $ W \cdot T $.

18) What is the relationship between degrees-of-freedom and the number of input-output equations that
can be solved


The **degrees of freedom (DoF)** represent the number of independent signal dimensions available for communication, determined by time, frequency, or spatial resources. For MIMO, DoF is $ \min(M, N) $; for time-frequency, it is approximately $ W \cdot T $.

19) Describe the reasoning why using **QPSK** is more efficient than using **BPSK** (in **AWGN** or fading
channels)

QPSK is more efficient than BPSK because it transmits **2 bits per symbol**, doubling the data rate for the same bandwidth while maintaining the same energy per bit ($E_b$) in AWGN or fading channels. This spectral efficiency makes QPSK favorable without increasing power requirements.

20) What is a deep fade?

A **deep fade** is a significant drop in the received signal's amplitude caused by **destructive interference** between multipath components in a fading channel. This results in a very low signal-to-noise ratio (SNR), increasing the likelihood of errors.

21) What are some ways that allow for the negative effect of deep fade be reduced?

In general, the effects of deep fades can be reduced by improving **signal robustness** through redundancy, adaptability, and leveraging multiple independent paths or resources to ensure reliable communication under varying channel conditions.

More specifically, to reduce the effects of deep fades:  
1. **Diversity** (time, frequency, spatial).  
2. **Channel Coding** (e.g., LDPC).  
3. **Power Control**.  
4. **Interleaving**.  
5. **Adaptive Modulation**.  
6. **RAKE Receiver** (for CDMA).



22) What is a valid statistical characterization for the fading coefficients, and their magnitude square?


- **Fading Coefficients ($h$)**: $ h \sim \mathcal{CN}(0, \sigma_h^2) $ (complex Gaussian).  
- **Magnitude Square ($|h|^2$)**: (power gain) Follows a **Rayleigh distribution** if $ h $ is zero-mean, or a **Rician distribution** if $ h $ has a line-of-sight component. Expected value: $ \mathbb{E}[|h|^2] = \sigma_h^2 $.

23) What is the average probability of error (averaged over the fading realizations), in a SISO Rayleigh
fading channel (high snr approximation)?


For a SISO Rayleigh fading channel at high SNR, the **average probability of error** is approximately:  
$
P_e \approx \frac{1}{2 \cdot \text{SNR}}.
$

24) What is the average probability of error (averaged over the fading realizations), in a $1 × n_r$ SIMO
Rayleigh fading channel (high snr approximation)?


In a **1 × $n_r$ SIMO Rayleigh fading channel** at high SNR, the **average probability of error** is:  
$
P_e \approx \frac{1}{(2 \cdot \text{SNR})^{n_r}}.
$

25) What is the average probability of error (averaged over the fading realizations), in a $1 × n_r$ SIMO
Rayleigh fading channel (high snr approximation)?



26) What is temporal, spatial, and frequency diversity


- **Temporal Diversity**: Transmit over different times to combat time-varying fading.  
- **Spatial Diversity**: Use multiple antennas for independent signal paths.  
- **Frequency Diversity**: Transmit over multiple frequencies to mitigate frequency-selective fading.

27) Give examples of when is temporal, spatial, and frequency diversity suitable (in terms of coding
duration $T$ , of $T_c$ , $W_c$ , $T_d$ and $W$ (signal bandwidth)


1. **Temporal Diversity**: **Coding duration** $ T $ **longer than the coherence time** $ T_c $, i.e., $ T > T_c $. 
2. **Spatial Diversity**: when **multiple antennas** are available
3. **Frequency Diversity**: **signal bandwidth** $ W $ **larger than the coherence bandwidth** $ W > W_c $. 

28) Describe the standard MIMO channel model

The **MIMO channel model** is:  
$
\mathbf{y} = \mathbf{H} \mathbf{x} + \mathbf{n},
$
where:
- $ \mathbf{y} \in \mathbb{C}^{N_r \times 1} $: Received signal,  
- $ \mathbf{H} \in \mathbb{C}^{N_r \times N_t} $: Channel matrix ($ h_{ij} \sim \mathcal{CN}(0, 1) $ for Rayleigh fading),  
- $ \mathbf{x} \in \mathbb{C}^{N_t \times 1} $: Transmitted signal,  
- $ \mathbf{n} \sim \mathcal{CN}(0, \sigma_n^2 \mathbf{I}) $: AWGN.  

It models interactions between $ N_t $ transmit and $ N_r $ receive antennas, supporting diversity or spatial multiplexing.

29) Describe the rank criterion in MIMO communications

The **rank criterion** in MIMO communications states that the channel matrix $ \mathbf{H} $ must have **rank $ r $** to support $ r $ independent data streams. Maximum spatial multiplexing is achieved when $ \text{rank}(\mathbf{H}) = \min(N_t, N_r) $. Higher rank also improves diversity and reliability.

30) Describe the rate of the Alamouti code carrying QPSK elements

The **Alamouti code** with **QPSK elements** transmits 2 QPSK symbols over 2 time slots, achieving a **rate of 1**, as $ R = \frac{\text{symbols transmitted}}{\text{time slots}} = \frac{2}{2} = 1 $.

31) How many degrees of freedom can you have in a
- SISO channel
- $n_t$ × 1 MISO channel
- $n_t$ × nr MIMO channel

- **SISO**: $ \text{DoF} = 1 $.  
- **MISO ($ n_t \times 1 $)**: $ \text{DoF} = 1 $.  
- **MIMO ($ n_t \times n_r $)**: $ \text{DoF} = \min(n_t, n_r) $.  

32) Why is the repetition code (for time diversity) very inefficient?

Repetition codes are inefficient because they reduce the data rate, waste bandwidth and time resources, and require more energy compared to advanced coding techniques that achieve better reliability with less redundancy.

33) Describe the relation between the cardinality of the code $|\mathcal{X} |$, the rate of transmission $R$ and the coding duration $T$

The relation is:  
$
|\mathcal{X}| = 2^{R \cdot T},
$
where $ |\mathcal{X}| $ is the code's cardinality, $ R $ is the transmission rate (bits/sec), and $ T $ is the coding duration.


