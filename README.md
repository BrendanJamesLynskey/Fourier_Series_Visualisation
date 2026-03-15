# Fourier Series Visualisations

Interactive explorations of Fourier series approximations — build periodic waveforms term by term and watch Gibbs phenomenon at discontinuities.

### [Launch App](https://brendanjameslynskey.github.io/Fourier_Series_Visualisation/)

---

## What is this?

Every periodic function can be decomposed into a sum of sines and cosines — its **Fourier series**. This tool lets you pick a target waveform and watch the approximation improve as you add harmonics one by one. The individual harmonic components are drawn alongside the partial sum so you can see exactly how each term shapes the result.

At discontinuities (like the jumps in a square wave) the partial sum always overshoots the target by about 9%, no matter how many terms you include. This is the **Gibbs phenomenon**, and the app highlights it with an annotation whenever it appears. The spectrum panel below the main plot shows the magnitude of each Fourier coefficient as a bar chart, giving a frequency-domain perspective on the same information.

Everything runs client-side in a single HTML file — no build step, no server, no dependencies to install.

## Waveforms

| Waveform | Key property |
|---|---|
| **Square wave** | Odd harmonics only, classic Gibbs overshoot |
| **Sawtooth** | All harmonics, amplitudes ~ 1/n |
| **Triangle** | Odd harmonics, amplitudes ~ 1/n² (fast convergence) |
| **Pulse train** | Sinc-shaped spectrum, tuneable duty cycle |
| **Half-wave rectified sine** | Even harmonics dominate |
| **Full-wave rectified sine** | Even cosine harmonics, rapid convergence |
| **Parabolic wave** | Connected to the Basel problem (π²/6) |
| **Trapezoidal wave** | Smoothed square wave, sinc × 1/n² decay |

## Features

- **Adjustable harmonics** — slider from 1 to 50 terms
- **Target overlay** — dashed line shows the exact waveform you are approximating
- **Individual harmonics** — each component drawn in a distinct colour
- **Frequency spectrum** — bar chart of Fourier coefficient magnitudes
- **Gibbs phenomenon annotation** — highlighted automatically at discontinuities
- **Interactive plots** — drag to pan, scroll to zoom, double-click to reset (Plotly.js)
- **Fully responsive** — works on desktop and mobile
- **Zero dependencies** — single HTML file served via GitHub Pages

## Built with

- [Plotly.js](https://plotly.com/javascript/) for interactive plotting
- Vanilla HTML / CSS / JS — no build step, no dependencies to install
