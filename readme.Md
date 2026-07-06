<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=700&size=32&pause=1000&color=00D4FF&center=true&vCenter=true&width=700&lines=Auto-Formation+%E2%80%94+Deep+Learning;From+First+Principles;No+Libraries.+Just+Math.+Just+NumPy." alt="Typing SVG" />

<br/>

<img src="https://img.shields.io/badge/PhD-ISTI%20%7C%20UM6P-00D4FF?style=for-the-badge&logoColor=white"/>
<img src="https://img.shields.io/badge/Supervisor-Dr.%20Kaoutar%20Sefrioui-7B61FF?style=for-the-badge"/>
<img src="https://img.shields.io/badge/Stack-NumPy%20only-FF6B35?style=for-the-badge&logo=numpy&logoColor=white"/>
<img src="https://img.shields.io/badge/Status-Active-00FF88?style=for-the-badge"/>

<br/><br/>

> *"Master every model from scratch — full mathematical derivation, hand-calculated verification, numpy implementation. No shortcuts."*

</div>

---

## 🧭 Roadmap

```
NN          ████████████████████░░░░  done ✅
CNN         ████████████████░░░░░░░░  done ✅
RNN/LSTM    ░░░░░░░░░░░░░░░░░░░░░░░░  upcoming
Transformers░░░░░░░░░░░░░░░░░░░░░░░░  upcoming
AE/VAE/GAN  ░░░░░░░░░░░░░░░░░░░░░░░░  upcoming
GNN         ░░░░░░░░░░░░░░░░░░░░░░░░  upcoming
Active Lrn  ░░░░░░░░░░░░░░░░░░░░░░░░  upcoming
```

| Module | Topics | Status | Notebook |
|--------|---------|--------|----------|
| **01 — NN** | Neuron, Forward Pass, Backprop, Optimizers, Regularization | ✅ Complete | [`01_NN/nn_scratch.ipynb`](./01_NN/nn_scratch.ipynb) |
| **02 — CNN** | Convolution, Pooling, im2col, LeNet from scratch | ✅ Complete | [`02_CNN/cnn_scratch.ipynb`](./02_CNN/cnn_scratch.ipynb) |
| **03 — RNN/LSTM** | Vanishing gradient, Gates, Sequence modeling | 🔄 In progress | — |
| **04 — Transformers** | Self-attention, Multi-head, Positional encoding | ⏳ Upcoming | — |
| **05 — AE/VAE/GAN** | Latent space, Reparameterization, Adversarial training | ⏳ Upcoming | — |
| **06 — GNN** | Message passing, GCN, GAT, GraphSAGE | ⏳ Upcoming | — |
| **07 — Active Learning** | Query strategies, Uncertainty sampling | ⏳ Upcoming | — |

---

## 01 — Neural Networks (NN)

### Architecture

```
INPUT            HIDDEN LAYER 1       HIDDEN LAYER 2        OUTPUT

  x₁ ──────────► [N₁] ─────────────► [N₄] ───────────────►
     ╲            [N₂]                [N₅]                   ŷ = σ(z)
      ╲──────────► [N₃] ─────────────►
  x₂ ──────────►
                  ReLU                ReLU

  z[l] = W[l] · a[l-1] + b[l]    ← one matrix multiply per layer
  a[l] = g( z[l] )                ← non-linearity applied elementwise
```

### Why Non-Linearity is Non-Negotiable

```
Without g:   W²(W¹x) = (W²W¹)x = W'x   →  depth buys nothing
With g:      each layer transforms the representation space non-linearly
             → network can approximate any continuous function (UAT)
```

### Activation Functions

```
SIGMOID                   TANH                    ReLU
  1 ┤    ╭────           1 ┤   ╭────             ╱
    │   ╱                0 ┤──╳                 ╱
0.5 ┤──╳                   │   ╲               ╱
    │ ╱                 -1 ┤    ╰────      ────╯
  0 ┤╱                     └─────          └─────
    └─────  z               z                z

σ(z) = 1/(1+e⁻ᶻ)         tanh(z)             max(0, z)
σ'  = σ(1-σ)              1 - tanh²(z)        1 if z>0, else 0

Vanishing gradient:  σ and tanh → derivative ≈ 0 at large |z|
                     multiplied across layers → early layers stop learning
Solution:            ReLU → derivative = 1 for z>0, no decay
```

### Backpropagation — Chain Rule Layer by Layer

```
FORWARD PASS                         BACKWARD PASS

x → z¹=W¹x+b¹ → a¹=g(z¹) → z²=W²a¹+b² → a²=σ(z²) → L
                                    ↑                ↑
                               δ²= a² - y       (sigmoid + BCE
                                    ↓             simplification)
                   δ¹ = (W²)ᵀδ² ⊙ g'(z¹)
                                    ↓
                        dW¹ = δ¹ · (x)ᵀ
                        db¹ = δ¹
```

**Complete algorithm:**
```
1.  Forward pass → cache every z[l] and a[l]
2.  δ[L]  = a[L] - y                             (output layer)
3.  δ[l]  = (W[l+1])ᵀ · δ[l+1]  ⊙  g'(z[l])    (hidden layers, l=L-1..1)
4.  dW[l] = δ[l] · (a[l-1])ᵀ
5.  db[l] = δ[l]
6.  W[l]  := W[l] - η · dW[l]
```

### Training Loss — XOR Dataset (1000 epochs)

```
0.70 │▓▓
0.65 │  ▓▓▓
0.60 │     ▓▓▓
0.55 │        ▓▓▓▓
0.50 │            ▓▓▓▓▓▓▓
0.45 │                   ▓▓▓▓▓▓▓▓▓
0.40 │                            ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓
     └──────────────────────────────────────────────────────  Epoch
     0        100       200       400                    1000
```

### Optimizers

```
SGD:       W := W - η·g
Momentum:  v := βv - η·g   ;   W := W + v             (β ≈ 0.9)
Adam:      m := β₁m+(1-β₁)g  ;  v := β₂v+(1-β₂)g²
           W := W - η · m̂ / (√v̂ + ε)                 (β₁=0.9, β₂=0.999)
```

### Weight Initialization

```
W = 0          →  symmetry: all neurons identical → whole layer = 1 neuron
W large rand   →  saturates sigmoid/tanh from step 1
Xavier:  N(0, 1/nᵢₙ)    →  keeps variance stable, sigmoid/tanh
He:      N(0, 2/nᵢₙ)    →  compensates ReLU zeroing half inputs, ReLU
```

### Verified Numerical Example (hand-calculated then numpy-verified)

```
Input:  x=[2, 3],  y_true=1
W1=[[0.5,1],[1,-0.5]], b1=[0,1], W2=[1,1], b2=-2

FORWARD
  z1 = [4.0,  1.5]        W1·x + b1
  a1 = [4.0,  1.5]        ReLU (both positive)
  z2 = 3.5                W2·a1 + b2
  a2 = 0.9707             σ(3.5)  ← prediction
  L  = 0.0297             BCE loss

BACKWARD
  δ2  = -0.0293           a2 - y
  dW2 = [-0.1172,-0.0440]
  δ1  = [-0.0293,-0.0293]
  dW1 = [[-0.0586,-0.0879],[-0.0586,-0.0879]]

AFTER UPDATE  (η=0.1)
  W2  = [1.0117, 1.0044]  ✓
  W1  = [[0.5059,1.0088],[1.0059,-0.4912]]  ✓
```

---

## 02 — Convolutional Neural Networks (CNN)

### Why CNN for Images?

```
Image 256×256×3 → 196,608 pixels

Fully Connected:  196,608 × 1000 neurons = 196,608,000 parameters  ← overfits
CNN (32 filters of 3×3×3):              = 864 parameters           ← efficient

Key idea: weight sharing — same filter slides over the whole image
```

### The Convolution Operation

```
INPUT (5×5)                FILTER (3×3)           OUTPUT (3×3)

 1  2  3  1  0             1  0  1
 4  5  6  2  1      *      0  1  0       =      (0,0) (0,1) (0,2)
 7  8  9  3  2             1  0  1              (1,0) (1,1) (1,2)
 1  2  3  1  0                                  (2,0) (2,1) (2,2)
 0  1  2  0  1

At (0,0): element-wise multiply top-left 3×3 patch with filter → sum → one number
Slide right (stride=1) → fill next column. Slide down → next row.

Output size: (Input - Filter + 2·Pad) / Stride + 1
Example:     (5 - 3 + 0) / 1 + 1 = 3
```

### LeNet-Style Architecture

```
INPUT      CONV→ReLU    POOL       CONV→ReLU    POOL      FC        OUTPUT
32×32×1 → 28×28×6  → 14×14×6 → 10×10×16 → 5×5×16 → 120  →  10
          5×5 kernel   2×2 max    5×5 kernel  2×2 max            softmax
          156 params   0 params   2,416 params  0 params

Early layers  →  edges, colors
Middle layers →  textures, shapes
Deep layers   →  object parts, class detectors
```

### Max Pooling

```
FEATURE MAP (4×4)         MAX POOL 2×2, stride=2      OUTPUT (2×2)

  1  3  2  4                                             3   4
  5  6  7  8      →        take max per 2×2 region  →   7   8
  3  1  2  0
  4  5  6  7                                             5   7

No learnable parameters. Reduces spatial size by 2×. Keeps strongest signal.
Backward: gradient flows only to the position that held the max value.
```

### Backward Through Convolution

```
FORWARD:   Z = conv(W, X)         filter slides over input
BACKWARD:
  dL/dW = conv(X, dL/dZ)         correlate input patches with upstream gradient
  dL/dX = full_conv(W_rot180, dL/dZ)   rotate filter, full padding, convolve
```

### Training Loss — MNIST Subset (30 epochs)

```
2.30 │▓▓
2.00 │  ▓▓▓
1.60 │     ▓▓▓
1.20 │        ▓▓▓▓
0.80 │            ▓▓▓▓▓▓
0.50 │                  ▓▓▓▓▓▓▓
0.30 │                         ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓
     └──────────────────────────────────────────────────  Epoch
     0       5      10      15      20                30

Final test accuracy: ~94%  (numpy only, no deep learning libraries)
```

---

## 📐 Notation Reference

| Symbol | Meaning |
|--------|---------|
| `W[l]` | Weight matrix layer l — shape `(n[l], n[l-1])` |
| `b[l]` | Bias vector layer l — shape `(n[l], 1)` |
| `z[l]` | Pre-activation: `W[l]·a[l-1] + b[l]` |
| `a[l]` | Post-activation: `g(z[l])` |
| `δ[l]` | Error signal: `dL/dz[l]` |
| `η` | Learning rate |
| `⊙` | Element-wise (Hadamard) product |
| `g'` | Derivative of activation function |

---

## 📚 Resources

| Resource | Role |
|----------|------|
| [CS231n — Stanford](https://cs231n.github.io/) | Primary course reference |
| [CS231n — NN Part 1](https://cs231n.github.io/neural-networks-1/) | Architecture & activations |
| [CS231n — Backprop](https://cs231n.github.io/optimization-2/) | Chain rule & gradient flow |
| [CS231n — Case Study](https://cs231n.github.io/neural-networks-case-study/) | Full numpy implementation |
| [CS231n — CNN](https://cs231n.github.io/convolutional-networks/) | Conv layers & pooling |
| Deep Learning — Goodfellow et al. | Mathematical foundations |

---

<div align="center">

**Khalil Moujibi** · PhD Researcher — AI for Chemistry · UM6P / ISTI · 2026

*Doctoral research: HieroRetro — Transformer-based retrosynthesis prediction*

</div>
