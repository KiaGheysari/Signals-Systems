# Signals and Systems Project: License Plate Recognition (LPR) System

This project, completed for the **Signals and Systems** course at Sharif University of Technology, involved the design and implementation of a functional **License Plate Recognition (LPR)** system. The system leverages core signal and image processing techniques to tackle both ideal and challenging real-world scenarios, demonstrating a practical application of theoretical concepts like correlation, filtering, and sampling.

## Project Overview

The goal was to build a simplified yet robust LPR pipeline capable of accurately segmenting and identifying characters from license plate images. The project was structured into two main challenges to test the system's resilience: an **Ideal Case** with clean images and a **Realistic Case** with images degraded by simulated motion blur and noise.

## Core Concepts & Techniques

*   **2D Correlation for Template Matching:** The mathematical foundation for character recognition, comparing segmented image patches against a library of reference characters to find the best match.
*   **Image Degradation Modeling:** Understanding how real-world blur can be modeled as a linear system (e.g., a 1D IIR filter) and its impact on image quality.
*   **Inverse Filtering for Deblurring:** Designing and applying a deconvolution filter to reverse blurring effects and reconstruct a cleaner image from its degraded version.
*   **Sampling Theory & Resolution Analysis:** Investigating the effects of spatial downsampling (resolution reduction) on the system's ability to correctly identify characters.

## Implementation Pipeline

### 1. Ideal Case Processing
*   **Image Segmentation:** Developed an algorithm to automatically locate and extract individual character bounding boxes from a full license plate image.
*   **Correlation-Based Recognition:** Implemented a robust character identification system by calculating the correlation between each segmented character and the provided templates of digits and letters.
*   **Resolution Robustness Analysis:** Systematically downsampled input images to determine the **minimum resolution** at which the system could maintain 100% accuracy, highlighting the limits imposed by sampling theory.

### 2. Realistic Case Processing (Deblurring Challenge)
*   **Blur Analysis:** Character recognition failed on blurred images, confirming the need for pre-processing.
*   **Blur Parameter Estimation:** Analyzed the degraded images to estimate the parameter `p` of the known blur kernel transfer function `H_blur(z) = (1-p)/(1-pz⁻¹)`.
*   **Inverse Filter Design & Application:** Designed and applied an appropriate inverse/deblurring filter to effectively restore image clarity.
*   **Full Pipeline Integration:** Fed the deblurred images into the segmentation and recognition pipeline, successfully recovering the license plate text.
*   **Noise Frequency Analysis:** For bonus tasks, performed frequency domain analysis (using FFT) on noisy images to identify and compare their noise characteristics without additional code.

## Key Insights & Results

*   Successfully demonstrated that **1D signal processing techniques** (correlation, IIR filtering) can be effectively extended and applied to **2D image processing** tasks.
*   Proved the critical importance of **image restoration** (deblurring) as a pre-processing step for computer vision systems operating in non-ideal conditions.
*   Quantified the trade-off between image resolution and recognition accuracy, empirically establishing the system's operational limits.
*   The final system accurately recognized license plates in both ideal and realistically degraded scenarios, showcasing a complete, end-to-end signal processing solution.
