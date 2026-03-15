# Fourier Series Visualisations

An interactive tool for building periodic waveforms term by term from their Fourier series — watch convergence in real time and explore the Gibbs phenomenon at discontinuities.

### [Launch App](https://brendanjameslynskey.github.io/Fourier_Series_Visualisation/)

---

## What is this?

In 1807, Joseph Fourier made a remarkable claim: any periodic function can be decomposed into a sum of sines and cosines. This idea — the **Fourier series** — turned out to be one of the most powerful tools in mathematics, physics, and engineering. It bridges the **time domain** (what a signal looks like) and the **frequency domain** (which sinusoidal components it contains), and underpins everything from audio compression and telecommunications to quantum mechanics and medical imaging.

This tool lets you pick a target waveform and build up its Fourier approximation harmonic by harmonic. A slider controls how many terms are included, from a single fundamental frequency up to 50 harmonics. Each individual component is drawn in its own colour so you can see exactly how it contributes to the emerging shape. Below the main plot, a bar-chart spectrum shows the magnitude of every Fourier coefficient, giving a frequency-domain view of the same information.

The mathematics is visible everywhere. **Odd functions** like the square wave and sawtooth produce only sine terms; **even functions** like the full-wave rectified sine produce only cosine terms. The rate at which coefficients decay determines how quickly the series converges: a triangle wave's 1/n² decay gives a smooth, fast-converging approximation, while a square wave's 1/n decay is far slower. At **discontinuities** — the abrupt jumps in a square wave or sawtooth — the partial sum always overshoots the target by roughly 9%, no matter how many terms you add. This is the **Gibbs phenomenon**, and the app automatically annotates it whenever it appears. These are not just mathematical curiosities: understanding harmonic content, spectral roll-off, and ringing at transitions is essential in signal processing, electronics, and acoustics.

## Waveforms

| Category | Waveforms |
|----------|-----------|
| **Classic periodic** | Square wave, Sawtooth, Triangle |
| **Pulse trains** | Pulse train (d = π/2), Narrow pulse (d = π/4), Wide pulse (d = 3π/4) |
| **Rectified sinusoids** | Half-wave rectified sine, Full-wave rectified sine |
| **Smooth / special** | Parabolic wave (Basel problem), Trapezoidal wave |

**Square wave** — Only odd harmonics, amplitudes ~ 1/n. The textbook example of Gibbs phenomenon: ~9% overshoot at every discontinuity regardless of the number of terms.

**Sawtooth** — All harmonics present, amplitudes ~ 1/n. A linearly rising ramp that resets abruptly, producing visible Gibbs ringing at the jump.

**Triangle** — Only odd harmonics, amplitudes ~ 1/n². The extra factor of 1/n means convergence is dramatically faster than the square wave. Continuous everywhere, so no Gibbs overshoot.

**Pulse train** (and Narrow / Wide variants) — Spectrum follows a **sinc envelope**, with the pulse width controlling the spacing of spectral nulls. Narrower pulses spread energy across more harmonics; wider pulses concentrate it in the low frequencies. This sinc-shaped spectrum is fundamental to sampling theory and digital signal processing.

**Half-wave rectified sine** — The waveform produced by a half-wave rectifier circuit. Even harmonics dominate the spectrum; the fundamental sine term comes through unscaled.

**Full-wave rectified sine** — The absolute value of sin(x), equivalent to the output of a full-wave bridge rectifier. Only even cosine harmonics appear, and convergence is rapid because the function is continuous.

**Parabolic wave** — A periodic extension of x². Coefficients decay as 1/n², giving fast convergence. Evaluating this series at x = π famously yields the **Basel problem** result: π²/6 = Σ 1/n².

**Trapezoidal wave** — A square wave with linear transition ramps of width π/3. The finite rise time introduces a sinc factor that multiplies the square wave's 1/n decay, producing an overall 1/n² roll-off. Continuous, so no Gibbs overshoot — a practical demonstration of how smoothing a waveform suppresses high-frequency content.

## Features

- **10 waveforms** spanning classic, pulse-train, rectified, and smooth/special categories
- **Adjustable harmonics** — slider from 1 to 50 terms, updating in real time
- **Target overlay** — dashed line shows the exact waveform being approximated
- **Individual harmonic traces** — each of the first 15 components drawn in a distinct colour so you can see how they combine
- **Fourier formula display** — the closed-form series expression shown alongside each waveform
- **Waveform descriptions** — educational notes on convergence behaviour, harmonic structure, and real-world connections
- **Frequency spectrum** — bar chart of Fourier coefficient magnitudes (|cₙ|) giving a frequency-domain perspective
- **Gibbs phenomenon annotation** — automatically detected and labelled at discontinuities, showing the percentage overshoot
- **Interactive plots** — drag to pan, scroll to zoom, double-click to reset (Plotly.js)
- **Dark theme** — carefully chosen colour palette with gradient header and high-contrast plot backgrounds
- **Fully responsive** — works on desktop and mobile
- **Zero dependencies** — single HTML file, no build step, served via GitHub Pages

## Built with

- [Plotly.js](https://plotly.com/javascript/) for interactive plotting
- Vanilla HTML / CSS / JS — no build step, no dependencies to install
