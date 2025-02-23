# Scale-Invariant Edge Detection
## Overview
This project explores scale-invariant feature detectors in the context of edge detection. The primary objective is to analyze how different kernel sizes impact edge detection accuracy. By applying first-derivative-based edge detection, we compute gradient magnitudes using convolution with different kernel sizes, allowing us to examine scale dependence and sensitivity.

## Methodology
The edge detection process follows these key steps:

Partial Differential Kernels

The kernel values are structured using v ∈ {−1, 0, 1}.
Kernels are designed to detect edges in the x-direction and y-direction separately:
x-direction:
Zeros in the middle row.
Negative values in the top half.
Positive values in the bottom half.
y-direction:
Zeros in the middle column.
Negative values on the left half.
Positive values on the right half.
The kernel size is always an odd-length square (e.g., 3×3, 5×5).
The center pixel is the focus of convolution operations.
Multi-Scale Edge Detection

The function takes an input image 𝐼 and applies convolution using multiple kernel sizes.

The kernel max size (𝑠) determines the range of odd-sized kernels used (e.g., for 𝑠 = 13, the function applies 3×3, 5×5, …, 13×13 kernels).

For each kernel size 𝑛, the gradient magnitude Magₙ(𝐼(𝑖, 𝑗)) is computed as:

Mag
𝑛
(
𝐼
(
𝑖
,
𝑗
)
)
=
𝑥
2
+
𝑦
2
𝑛
2
Mag 
n
​
 (I(i,j))= 
n 
2
 
x 
2
 +y 
2
 
​
 
Cutoff Threshold (𝑡)

A threshold value 𝑡 is applied to filter out weak edges, ensuring only significant edges are detected.
## Implementation Details
The implemented function processes an input image 𝐼 using:

Convolution with multiple kernel sizes to examine edge scale invariance.
Gradient magnitude calculation for edge detection.
Threshold filtering to refine edge detection results.
## Expected Outcomes
By analyzing edge detection across multiple scales, this project provides insights into how kernel size affects feature detection accuracy, demonstrating the trade-offs between detail preservation and noise sensitivity.
