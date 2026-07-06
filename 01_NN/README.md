# 01 — Neural Networks

[← Back to main](../README.md) &nbsp;|&nbsp; **Status:** ✅ Complete

**Reference:** [CS231n NN Part 1](https://cs231n.github.io/neural-networks-1/) · [Backprop](https://cs231n.github.io/optimization-2/) · [Case Study](https://cs231n.github.io/neural-networks-case-study/)

---

## Files in this folder

| File | What it contains |
|------|-----------------|
| [`nn_scratch.ipynb`](./nn_scratch.ipynb) | NumPy implementation — relu, sigmoid, forward, backprop, training loop |

---

## Architecture

```
INPUT         HIDDEN 1 (ReLU)    HIDDEN 2 (ReLU)    OUTPUT (sigmoid)

  x₁ ───────► [N₁]
     ╲         [N₂] ────────────► [N₄] ────────────► ŷ
      ╲────────► [N₃]              [N₅]
  x₂ ───────►

Forward:   z[l] = W[l] · a[l-1] + b[l]   →   a[l] = g(z[l])
Backward:  δ[l] = (W[l+1])ᵀ · δ[l+1] ⊙ g'(z[l])   →   dW[l] = δ[l] · (a[l-1])ᵀ
```

---

## Concepts Mastered

### 1. The Neuron
```
z = w·x + b     weighted sum (pre-activation)
a = g(z)         non-linear activation
```
**Why g is mandatory:** W²(W¹x) = (W²W¹)x — without non-linearity, depth is useless.

### 2. Activation Functions

| Function | Formula | Derivative | Range | Note |
|----------|---------|------------|-------|------|
| Sigmoid | `1/(1+e⁻ᶻ)` | `σ·(1-σ)` | (0,1) | Vanishing gradient at extremes |
| Tanh | `(eᶻ-e⁻ᶻ)/(eᶻ+e⁻ᶻ)` | `1-tanh²` | (-1,1) | Better than sigmoid, still saturates |
| **ReLU** | `max(0,z)` | `1 if z>0, else 0` | [0,∞) | Default for hidden layers |

### 3. Loss Functions
```
MSE (regression):       L = (ŷ-y)²
BCE (binary classif.):  L = -[y·log(ŷ) + (1-y)·log(1-ŷ)]
CCE (multi-class):      L = -Σ y_c · log(ŷ_c)
```

### 4. Backpropagation — Full Algorithm
```
1. Forward pass → cache every z[l] and a[l]
2. δ[L] = a[L] - y                            (output, sigmoid+BCE)
3. δ[l] = (W[l+1])ᵀ·δ[l+1] ⊙ g'(z[l])      (hidden, l=L-1 down to 1)
4. dW[l] = δ[l]·(a[l-1])ᵀ   db[l] = δ[l]
5. W[l] := W[l] - η·dW[l]                    (gradient descent)
```

### 5. Verified Numerical Example
```
Setup: x=[2,3], y=1, lr=0.1
W1=[[0.5,1],[1,-0.5]], b1=[0,1], W2=[1,1], b2=-2

FORWARD
  z1 = [4.0, 1.5]     W1·x + b1
  a1 = [4.0, 1.5]     ReLU (both positive)
  z2 = 3.5             W2·a1 + b2
  a2 = 0.9707          σ(3.5)
  L  = 0.0297          BCE loss

BACKWARD
  δ2  = -0.0293
  dW2 = [-0.1172, -0.0440]
  δ1  = [-0.0293, -0.0293]
  dW1 = [[-0.0586,-0.0879],[-0.0586,-0.0879]]

AFTER UPDATE (η=0.1)
  W2 = [1.0117, 1.0044]  ✓
  W1 = [[0.5059,1.0088],[1.0059,-0.4912]]  ✓
```

### 6. Optimizers
```
SGD:       W := W - η·g
Momentum:  v := β·v - η·g  ;  W := W + v        β≈0.9
Adam:      m̂/(√v̂+ε)                              β₁=0.9, β₂=0.999  ← default
```

### 7. Weight Initialization
```
Zero   → symmetry problem: all neurons identical → broken
Xavier → W ~ N(0, 1/nᵢₙ)    for sigmoid/tanh
He     → W ~ N(0, 2/nᵢₙ)    for ReLU
```

### 8. Regularization
```
L2:            dW_total = dW + λW
Dropout:       zero each neuron with prob p, scale survivors by 1/(1-p)
Early stop:    stop when val_loss rises while train_loss falls
```
