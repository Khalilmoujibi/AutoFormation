# NN — My Progress Log

## What I can explain out loud (without notes)

### The neuron
A single neuron takes inputs, multiplies each one by a weight (how much that input matters), adds them all up plus a bias offset, then passes the result through an activation function.

In math: `z = w·x + b` then `a = g(z)`

### Why activation functions are not optional
Without a non-linearity, stacking layers is pointless:
```
W2(W1·x) = (W2·W1)·x = W'·x
```
Two layers collapse into one. A deep network with no activations has the same power as a single neuron — a straight line. The non-linearity is what lets the network bend and fit complex shapes.

### From neuron to layer — the matrix
A layer is just many neurons reading the same input. Instead of computing each one separately, we stack their weights into a matrix W (one row per neuron). Then:
```
z = W·x + b
```
Row 1 of W dot x = neuron 1's weighted sum. Row 2 of W dot x = neuron 2's. All computed in one operation.

### ReLU
Rule: if input is positive, keep it. If negative, output 0.
```
ReLU(5)  = 5
ReLU(-3) = 0
```
Derivative: 1 where z > 0, else 0.

### The forward pass
Repeat layer-by-layer:
```
z[l] = W[l] · a[l-1] + b[l]
a[l] = g(z[l])
```
Cache every z and a — backprop needs them.

### Loss
Measures how wrong the prediction is. One number.
Binary cross-entropy: `L = -[y·log(y_hat) + (1-y)·log(1-y_hat)]`

### Backpropagation
Pass the error backward, layer by layer, using the chain rule.
- Output: `δ[L] = a[L] - y` (with sigmoid + BCE)
- Hidden: `δ[l] = (W[l+1])ᵀ · δ[l+1] ⊙ g'(z[l])`
- Gradients: `dW[l] = δ[l] · (a[l-1])ᵀ`

### Gradient descent
Move every weight a small step in the direction that reduces loss:
```
W := W - η · dW
```

---

## What I still need to solidify

- [ ] Re-derive the sigmoid derivative on paper from scratch
- [ ] Explain the Adam optimizer equations from memory
- [ ] Debug the XOR training convergence issue (dead ReLU problem)
- [ ] Re-write the full notebook myself without looking at any reference

---

## Key dates

| Date | Milestone |
|------|-----------|
| June 2026 | Started NN auto-formation |
| TBD | NN fully mastered — moving to CNN |
