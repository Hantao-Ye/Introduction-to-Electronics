# Chapter 3

## 3-1 Ideal Diode

The **ideal diode** may be considered to be the most fundamental ==nonlinear== circuit element, which has two nodes:

- **anode**: the positive terminal
- **cathode**: the negative terminal

<div align = center><img height = 200 src = "../assets/ch3-1.png"></div>

If a negative voltage is applied

- no current flows
- reverse biased
- **cut off**

If a positive current is applied

- zero voltage drop
- forward biased
- **turn on**

<div align = center><img height = 600 src = "../assets/ch3-2.png"></div>

### A simple Application: The Rectifier

<div align = center><img height = 700 src = "../assets/ch3-3.png"></div>

### Another Application: Diode Logic Gates

<div align = center><img height = 400 src = "../assets/ch3-4.png"></div>

For the figure (a), the circuit implements with the **logic OR function**

$$
Y = A+B+C
$$

For the figure (b), the circuit implements with the **logic AND function**

$$
Y = A\cdot B\cdot C
$$

### The Constant-Voltage-Drop Model

The simplest and most widely used diode model is the constant-voltage-drop model. This model is based on the observation that a forward-conducting diode has a voltage drop that varies in a relatively narrow range from 0.6 to 0.8 volt. The model assumes **this voltage to be constant at a value of 0.7 volt**

<div align = center><img height = 400 src = "../assets/ch3-5.png"></div>

## 3-2 Special Diode Types

### LED

<div align = left><img height = 300 src = "../assets/ch3-6.png"></div>

The light-emitting diode converts a forward current into light and the current on the diode could be determined by

$$
i_D = \frac{V_{CC}-V_D}{R}
$$

> typical current ratings ranges from around 1 mA to 20 mA depending on the size of a LED

### Zener Diodes

<div align = left><img height = 300 src = "../assets/ch3-7.png"></div>

A Zener diode is a special type of diode designed to reliably allow current to flow "backwards" when a certain set reverse voltage, where it is be equivalently expressed as 

$$
V_Z = V_{Z0} +r_ZI_Z
$$

## 3-3 Rectifier and Limiting Circuits

### The Half-Wave Rectifier

<div align = center><img height = 600 src = "../assets/ch3-8.png"></div>

$$
PIV = V_S
$$

> **peak inverse voltage (PIV)**: the voltage that the diode must be able to withstand without breakdown

### The Full-Wave Rectifier

<div align = center><img height = 600 src = "../assets/ch3-9.png"></div>

$$
PIV = 2V_S-V_D
$$

### The Bridge Rectifier

<div align = center><img height = 600 src = "../assets/ch3-10.png"></div>

$$
PIV = V_S-2V_D+V_D = V_S-V_D
$$

### The Peak Rectifier

<div align = center><img height = 900 src = "../assets/ch3-11.png"></div>

### Precision Half-Wave Rectifier

<div align = center><img height = 350 src = "../assets/ch3-13.png"></div>

### Limiter Circuits

<div align = center><img height = 900 src = "../assets/ch3-12.png"></div>

### Clamped Capacitor

<div align = center><img height = 250 src = "../assets/ch3-14.png"></div>

### Voltage Doubler

<div align = center><img height = 600 src = "../assets/ch3-15.png"></div>

