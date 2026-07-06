# 🧠 Auto-Formation — Deep Learning from Scratch

**PhD Student:** Khalil Moujibi  
**Program:** ISTI — Université Mohammed VI Polytechnique (UM6P)  
**Supervisor:** Dr. Kaoutar Sefrioui  
**Goal:** Master every model from scratch, with full mathematical understanding — no libraries, just numpy.

---

## 📋 Program

| # | Topic | Status |
|---|-------|--------|
| 1 | Neural Networks (NN) | 🔄 In progress |
| 2 | Convolutional Neural Networks (CNN) | ⏳ Upcoming |
| 3 | RNN / LSTM / GRU / Bi-LSTM | ⏳ Upcoming |
| 4 | Transformers + Attention Mechanism | ⏳ Upcoming |
| 5 | Autoencoders (AE, VAE, MAE) + GAN | ⏳ Upcoming |
| 6 | Graph Embeddings + GNN (GCN, GAT, GraphSAGE) | ⏳ Upcoming |
| 7 | Active Learning / Online Learning | ⏳ Upcoming |

---

## 📁 Structure

```
AutoFormation/
├── 01_NN/
│   ├── theory.md              ← Full theory notes (math + intuition)
│   ├── nn_scratch.ipynb       ← Implementation from scratch in numpy
│   └── progress.md            ← What I understand, what I can explain
├── 02_CNN/                    ← Coming next
└── ...
```

---

## 🎯 Approach

For each model, I follow this exact order:

1. **Intuition** — understand what the model does and why, before any math
2. **Mathematics** — derive every formula from scratch (forward pass, loss, backward pass, gradients)
3. **Implementation** — code it in numpy only, no deep learning libraries
4. **Verification** — test against hand-calculated values to confirm correctness
5. **Explanation** — be able to explain every line of code and every formula out loud

---

## ✅ Current progress — Neural Networks

### What I understand and can explain:

- What a single neuron computes: `z = w·x + b`, then `a = g(z)`
- Why activation functions are required (without them, stacking layers collapses to one linear function)
- How a layer is just many neurons computed at once via matrix multiplication `z = W·a + b`
- All activation functions: ReLU, Sigmoid, Tanh, Softmax — formulas and derivatives
- Loss functions: MSE, Binary Cross-Entropy, Categorical Cross-Entropy
- The full backpropagation algorithm derived from the chain rule
- Gradient descent and optimizers: SGD, Momentum, Adam
- Weight initialization: Xavier and He — and why initializing to zero breaks everything
- Regularization: L2, Dropout, Batch Normalization, Early Stopping

### What I implemented from scratch (numpy only):

- `relu(z)` and `relu_derivative(z)`
- `sigmoid(z)`
- `forward(x, W1, b1, W2, b2)` — full forward pass, all values cached
- `bce_loss(y_hat, y)` — binary cross-entropy
- `backward(...)` — full backpropagation with the chain rule
- `update(...)` — gradient descent weight update
- Full training loop on XOR dataset — 1000 epochs, loss decreasing

---

## 📚 Resources

- [CS231n — Neural Networks (Stanford)](https://cs231n.github.io/neural-networks-1/)
- [CS231n — Backpropagation](https://cs231n.github.io/optimization-2/)
- [CS231n — Case Study (from scratch)](https://cs231n.github.io/neural-networks-case-study/)
