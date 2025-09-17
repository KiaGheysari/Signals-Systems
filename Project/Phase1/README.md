# Signals and Systems Project: Advanced Noise Cancellation and Audio Steganography

This project, completed for the **Signals and Systems** course at Sharif University of Technology, explores advanced signal processing techniques for noise cancellation and information decoding. The core innovation involves implementing a **Deep Convolutional Autoencoder (DCAE)** as a sophisticated adaptive filter to surpass the performance of traditional FIR and IIR filters.

## Project Overview

The project is divided into two main phases: theoretical research and practical implementation. The goal was to understand various noise models and cancellation methods, then apply this knowledge to clean a corrupted audio signal and decode a hidden message using steganography techniques.

## Theoretical Research

*   **Noise Models:** Analysis and mathematical formulation of common noise types in discrete-time (Gaussian, Uniform, White, Impulse, and 50 Hz Power Line noise).
*   **Noise Cancellation Methods:** Investigation of traditional methods (FIR, IIR filtering) and advanced techniques (Wavelet Transform).
*   **Eigen Signals:** Study of orthogonal signal representations and their applications in signal processing.
*   **Adaptive Filtering:** In-depth research into the LMS algorithm, gradient descent, and convergence properties.

## Implementation & Key Components

### 1. Adaptive Noise Cancellation using a Deep Convolutional Autoencoder (DCAE)
*   **Data Generation:** A personal voice recording was captured and artificially corrupted with 50 Hz power line noise.
*   **Innovative Filtering:** Instead of a standard LMS-based adaptive filter, a **Deep Convolutional Autoencoder (DCAE)** was designed and trained to serve as a powerful non-linear adaptive filter. This model learns to map noisy audio segments to their clean counterparts in the time domain.
*   **Performance Benchmarking:** The performance of the DCAE was rigorously compared against classically designed FIR and IIR notch filters. Metrics included qualitative listening tests and quantitative analysis of signal-to-noise ratio (SNR) and waveform plots.
*   **Results:** The DCAE demonstrated superior performance in effectively suppressing the narrow-band noise while preserving the original voice signal's fidelity better than the linear filters.

### 2. LSB Audio Steganography Decoding
*   **Analysis:** Frequency domain analysis (via FFT) was performed on a provided noisy audio file to identify contaminating noise frequencies.
*   **Filter Design:** Based on the spectral analysis, a custom filter was designed to remove the noise without distorting the hidden message embedded in the Least Significant Bits (LSBs).
*   **Decoding:** The hidden text message was successfully extracted from the audio file by decoding the LSBs of the samples after the precise filtering process.

## Key Insights & Results

*   Proved that a **DCAE can act as a highly effective adaptive filter**, capable of learning complex, non-linear relationships between noisy and clean signals that traditional linear filters cannot model.
*   Demonstrated the practical challenges and solutions in filtering: the trade-off between noise removal and signal integrity.
*   Successfully applied theoretical concepts of frequency analysis and digital filtering to solve a real-world problem of data extraction from a noisy channel.

## Technologies & Methods Used

*   **Language:** Python
*   **Libraries:** NumPy, SciPy, Matplotlib, Librosa, SoundFile, TensorFlow/Keras (for DCAE implementation)
*   **Core Techniques:**
    *   Deep Learning (Convolutional Autoencoders)
    *   Digital Filter Design (FIR, IIR)
    *   Frequency Analysis (Fast Fourier Transform - FFT)
    *   Least Significant Bit (LSB) Steganography
*   **Concepts:** Adaptive Filtering, Noise Modelling, Signal Processing, Gradient Descent

---

This project highlights a strong foundational knowledge of signal processing theory and the ability to implement innovative, modern solutions (like deep learning) to solve classical engineering problems effectively. The use of a DCAE presents a novel approach to adaptive filtering that moves beyond conventional algorithms.
