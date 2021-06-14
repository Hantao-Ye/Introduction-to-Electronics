## Op Amp 

### Analysis Method

There are tree rules to analyze the op amp circuit

- ==**virtual short**==: $v_+=v_-$
- ==**virtual open**==: $i_+=0,i_-=0$
- ==**zero output resistance**==: $R_o=0$

### DC Imperfections

#### Offset Voltage

<div align = center><img height = 250 src = "../assets/ch2-10.png"></div>

The output voltage due to $V_{OS}$ is found to be 

$$
V_O =V_{OS}\Big[1+\frac{R_2}{R_1}\Big]
$$

#### Bias Currents

<div align = center><img height = 300 src = "../assets/ch2-12.png"></div>

The average value $I_B$ is called the **input bias current**

$$
I_B = \frac{I_{B1}+I_{B2}}{2}
$$

and the difference is called the **input offset current** and is given by

$$
I_{OS} = |I_{B1}-I_{B2}|
$$

- DC: $R_3 = R_1\|R_2$
- AC: $R_3 = R_2$

#### Finite Loop Gain

<div align = center><img height = 200 src = "../assets/ch2-13.png"></div>

$$
v_+-v_- = \frac{v_O}{A}\Rightarrow v_-=-\frac{v_O}{A}
$$

## BJT

### DC Analysis

<div align = center><img height = 600 src = "../assets/ch4-13.jpg"></div>

> **cut off** mode: $\|V_{BE}\|<0.5\;V$

### Small Signal Analysis

1. DC analysis, cut all capacitors and sig.
2. find $I_C$
3. cal $g_m$, $r_e$ and $r_\pi$ and draw the ac circuit
4. find $V_o/V_i$
5. find input and output resistance

<div align = center><img height = 870 src = "../assets/ch4-14.png"></div>
<div align = center><img height = 400 src = "../assets/ch4-15.png"></div>

## MOSFET

## DC Analysis

<div align = center><img height = 800 src = "../assets/ch5-9.png"></div>
<div align = center><img height = 810 src = "../assets/ch5-11.png"></div>

## Small Signal Analysis

1. DC analysis, cut all capacitors and sig.
2. find $I_D$ and $V_{OV}$
3. cal $g_m$ and draw the ac circuit
4. find $V_o/V_i$
5.  find input and output resistance

<div align = center><img height = 872 src = "../assets/ch5-12.png"></div>

## Filter

### Filter Specification

<div align = center><img height = 450 src = "../assets/ch6-2.png"></div>

- $\omega_p$: the passband edge
- $A_{max}$: the maximum allowed variation in passband transmission
- $\omega_s$: the stopband edge
- $A_{min}$: the minimum required stopband attenuation

### Butterworth Filter

<div align = center><img height = 450 src = "../assets/ch6-4.png"></div>

$$
\|T(j\omega)\| = \frac{1}{\sqrt{1+\epsilon^2\big(\frac{\omega}{\omega_p}\big)^2}}
$$

At the frequency of $\omega_p$

$$
\|T(j\omega)\| = \frac{1}{\sqrt{1+\epsilon^2}}
$$

Then the parameter $\epsilon$ determines $A_{max}$

$$
\begin{aligned}
    A_{max} &= 10\log{(1+\epsilon^2)}\\[2ex]
    \epsilon &= \sqrt{10^{A_{max}/10}-1}
\end{aligned}
$$

At the edge of stopband $\omega=\omega_s$, check the attenuation of the filter

$$
A(\omega_s) = 10\log{\Big[1+\epsilon^2(\omega_s/\omega_p)^{2N}\Big]}
$$

Find the lowest filter order $N$ such that $A(\omega_s)>A_{min}$

<div align = center><img height = 750 src = "../assets/ch6-5.png"></div>

Then the transfer function could be written as

$$
T(s) = \frac{K\omega_0^N}{(s-p_1)(s-p_2)\cdots(s-p_N)}
$$

- $\omega_0=\omega_p(1/\epsilon)^{1/N}$

### First Order Filters

The general first-order transfer function is given by

$$
T(s) = \frac{a_1s+a_0}{s+\omega_0}
$$

<div align = center><img height = 750 src = "../assets/ch6-7.png"></div>
<div align = center><img height = 400 src = "../assets/ch6-8.png"></div>

### Second Order Transfer Functions

<div align = center><img height = 750 src = "../assets/ch6-9.png"></div>
<div align = center><img height = 750 src = "../assets/ch6-10.png"></div>
<div align = center><img height = 400 src = "../assets/ch6-11.png"></div>

### Second-Order LCR Resonator

$$
\begin{aligned}
    \omega_0 &= \frac{1}{\sqrt{LC}}\\[2ex]
    Q &= \omega_0 CR
\end{aligned}
$$

#### Low-Pass Function

<div align = center><img height = 250 src = "../assets/ch6-12.png"></div>

$$
T(s) = \frac{Z_2}{Z_1+Z_2} = \frac{\omega_0^2}{s^2+s(\omega_0/Q)+\omega_0^2}
$$

> 2nd-order low-pass filters have **2 zeros** at $\infty$

#### High-Pass Function

<div align = center><img height = 250 src = "../assets/ch6-13.png"></div>

$$
T(s) = \frac{Z_2}{Z_1+Z_2} = \frac{s^2}{s^2+s(\omega_0/Q)+\omega_0^2}
$$

> 2nd-order high-pass filters have **2 zeros** at $s=0$

#### Band-Pass Function

<div align = center><img height = 250 src = "../assets/ch6-14.png"></div>

$$
T(s) = \frac{Z_2}{Z_1+Z_2} = \frac{(\omega_0/Q)s}{s^2+s(\omega_0/Q)+\omega_0^2}
$$

> 2nd-order band-pass filters have **1 zero** at $\infty$ and **1 zero** at $s=0$

#### Notch Function

<div align = center><img height = 250 src = "../assets/ch6-15.png"></div>

$$
T(s) = \frac{Z_2}{Z_1+Z_2} = a_2\frac{s^2+\omega_0^2}{s^2+s(\omega_0/Q)+\omega_0^2}
$$

> 2nd-order notch(bandstop) filters have **2 zeros** at $j\omega$ axis

### Op Amp-RC Resonator

<div align = center><img height = 350 src = "../assets/ch6-16.png"></div>

$$
L = \frac{C_4R_1R_3R_5}{R_2}
$$

The design of the circuit is usually selecting $R_1=R_2=R_3=R_5=R$ and $C_4=C$, which leads to $L = CR^2$

### KHN Biquad

$$
V_{hp}=KV_i-\frac{1}{Q}\frac{\omega_0}{s}V_{hp}-\frac{\omega_0^2}{s^2}V_{hp}
$$

<div align = center><img height = 250 src = "../assets/ch6-23.png"></div>

<div align = center><img height = 350 src = "../assets/ch6-24.png"></div>

$$
\begin{aligned}
    V_{hp} &= V_i \frac{R_3}{R_2+R_3}\Big(1+\frac{R_f}{R_1}\Big)+V_{bp}\frac{R_2}{R_2+R3}\Big(1+\frac{R_f}{R_1}\Big)-V_{lp}\frac{R_f}{R_1}\\[2ex]
           &= V_i \frac{R_3}{R_2+R_3}\Big(1+\frac{R_f}{R_1}\Big)+\Big(-\frac{\omega_0}{s}V_{hp}\Big)\frac{R_2}{R_2+R3}\Big(1+\frac{R_f}{R_1}\Big)-\Big(\frac{\omega_0^2}{s^2}V_{hp}\Big)\frac{R_f}{R_1}\\[2ex]
\end{aligned}
$$

- $CR=1/\omega_0$
- $R_f=R_1$
- $R_3/R_2=2Q-1$
- $K=2-(1/Q)$

<div align = center><img height = 200 src = "../assets/ch6-25.png"></div>

$$
\begin{aligned}
    V_o &= -(\frac{R_F}{R_H}V_{hp}+\frac{R_F}{R_B}V_{bp}+\frac{R_F}{R_L}V_{lp})\\[2ex]
        &= -V_i(\frac{R_F}{R_H}T_{hp}+\frac{R_F}{R_B}T_{bp}+\frac{R_F}{R_L}T_{lp})\\[2ex]
    \frac{V_o}{V_i} &= -K\frac{(R_F/R_H)s^2-s(R_F/R_B)\omega_0+(R_F/R_L)\omega_0^2}{s^2+s(\omega_0/Q)+\omega_0^2}
\end{aligned}
$$

### Tow–Thomas Biquad

<div align = center><img height = 350 src = "../assets/ch6-26.png"></div>

$$
\frac{V_o}{V_i} = -\frac{s^2\big(\frac{C_1}{C}\big)+s\frac{1}{C}\big(\frac{1}{R_1}-\frac{r}{RR_3}\big)+\frac{1}{C^2RR_2}}{s^2+s\frac{1}{QCR}+\frac{1}{C^2R^2}}
$$

- $r=\text{arbitrary}$
- $C=\text{arbitrary}$
- $R=1/\omega_0$

<div align = center><img height = 950 src = "../assets/ch6-27.png"></div>