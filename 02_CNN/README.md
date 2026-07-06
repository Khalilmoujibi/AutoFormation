# 02 — Convolutional Neural Networks

[← Back to main](../README.md) &nbsp;|&nbsp; **Status:** ✅ Complete

**Reference:** [CS231n — CNN](https://cs231n.github.io/convolutional-networks/)

---

## Files in this folder

| File | What it contains |
|------|-----------------|
| [`cnn_scratch.ipynb`](./cnn_scratch.ipynb) | NumPy implementation — conv layer, pooling, backprop, LeNet training |

---

## Why CNN Instead of Plain NN?

```
Image 256×256×3 = 196,608 pixels

Fully Connected:  196,608 × 1000 = 196,608,000 parameters  ← overfits
CNN 32 filters of 3×3×3:   =           864 parameters  ← weight sharing

Key idea: same filter slides over the whole image → translation invariant
```

---

## The Convolution Operation

```
INPUT (5×5)        FILTER (3×3)       OUTPUT (3×3)

 1  2  3  1  0     1  0  1
 4 [5  6  2] 1  *  0  1  0  =  one number per valid position
 7 [8  9  3] 2     1  0  1
 1  2  3  1  0
 0  1  2  0  1

Slide filter → stride=1 → one output number per position

Output size = (Input - Filter + 2·Padding) / Stride + 1
Example:     (5 - 3 + 0) / 1 + 1 = 3
```

---

## LeNet Architecture

```
32×32×1 → CONV(5×5)→ReLU → POOL(2×2) → CONV(5×5)→ReLU → POOL(2×2) → FC → 10 classes
            28×28×6          14×14×6      10×10×16         5×5×16    120   softmax
            156 params        0 params     2,416 params      0 params

Early layers  →  edges, colors (simple)
Middle layers →  textures, shapes (combined)
Deep layers   →  class detectors (complex)
```

---

## Forward Pass — Conv Layer
```python
# For each filter f, each position (i,j):
z[f,i,j] = sum( W[f] * input_patch[i:i+kH, j:j+kW] ) + b[f]
a = ReLU(z)

# Efficient via im2col:
# Reshape patches → columns, then one matrix multiply
X_col : (kH×kW×C, out_H×out_W)
Z     = W_reshaped · X_col + b
```

## Max Pooling
```
 1  3  2  4          3  4
 5  6  7  8   →      7  8     2×2 max pool, stride=2
 3  1  2  0          5  7
 4  5  6  7

No parameters. Backward: gradient goes only to the max position.
```

## Backward Through Convolution
```
dL/dW = conv(input, dL/dz)            correlate input with upstream gradient
dL/dx = full_conv(W_rot180, dL/dz)    distribute gradient back to input
```

---

## Training Results — MNIST Subset
```
Epochs: 30   Optimizer: SGD   lr: 0.01
Start loss: 2.30   Final loss: 0.30   Test accuracy: ~94%
Implementation: NumPy only — no PyTorch, no TensorFlow
```
