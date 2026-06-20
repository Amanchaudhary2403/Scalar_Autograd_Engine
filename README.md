<div align="center">
  <img src="assets/banner.svg" alt="ScalarGrad — animated computation graph banner" width="680"/>
</div>

---

# ScalarGrad — A Scalar Autograd Engine from Scratch

A minimal but fully functional automatic differentiation engine built on scalar values, with a neural network library layered on top. Think of it as a tiny PyTorch — every operation tracks its own gradient, and backpropagation is computed automatically via a topological sort of the computation graph.

---

## How It Works

At the core is a `Node` — a single scalar value that remembers:
- Its **data** (the number itself)
- Its **children** (what values it was computed from)
- Its **`_backward` function** (how to pass gradients back to those children)

When you call `.backward()` on a final output node, the engine:
1. Builds a **topological ordering** of the entire computation graph
2. Walks it **in reverse**, calling `_backward()` at each step
3. This accumulates `.grad` on every node — the derivative of the output with respect to that node

---

## Supported Operations

| Operation | Symbol / Method |
|-----------|----------------|
| Addition | `+` |
| Multiplication | `*` |
| Subtraction | `-` |
| Division | `/` |
| Power | `**` |
| Natural Log | `.log()` |
| Tanh | `.tanh()` |
| Sigmoid | `.sigmoid()` |
| ReLU | `.relu()` |

---

## Neural Network API

Built on top of `Node`, the library provides three composable building blocks:

```
Neuron  →  Layer  →  ANN
```

- **`Neuron(inp_size, activation)`** — a single neuron with He-uniform weight initialization
- **`Layer(n_inp, n_out, activation)`** — a fully-connected layer of neurons
- **`ANN(n_inp, list_layers, activations)`** — a full multi-layer network

Supported activations: `'relu'`, `'sigmoid'`, `'tanh'`, `'linear'`

---

## Example — XOR Problem

```python
X = [[0,0], [0,1], [1,0], [1,1]]
Y = [0, 1, 1, 0]

model = ANN(2, [4, 1], ['tanh', 'sigmoid'])

for epoch in range(5000):
    preds = [model(x) for x in X]
    loss = binary_cross_entropy_loss(preds, Y)

    for p in model.parameters(): p.grad = 0
    loss.backward()
    for p in model.parameters(): p.data -= 0.01 * p.grad
```

The model learns XOR — a non-linearly separable problem — using a hidden layer with `tanh` and an output layer with `sigmoid`.

---

## Loss Function

Binary Cross-Entropy is included out of the box:

```
loss = -[y · log(p) + (1 - y) · log(1 - p)]
```

Averaged over the batch, and fully differentiable through the `Node` graph.

---

## Computation Graph Visualizer

Every forward pass through `Node` builds a live computation graph. You can render it with `plot_grph()`:

```python
x = Node(2.0, label='x')
y = Node(3.0, label='y')
z = x * y + x
z.backward()

dot = plot_grph(z)
dot.render('graph', view=True)   # saves graph.svg and opens it
```

The visualizer uses **Graphviz** and renders an SVG with a dark-mode aesthetic:

- **White record boxes** — each `Node` shows its `data` and `grad` side by side
- **Purple circles** — operation nodes (`+`, `*`, `tanh`, etc.)
- **Dark red arrows** — data flow from inputs → operations → outputs

This makes it easy to visually trace how a value was computed and verify that gradients are flowing correctly during backprop.

---

## Project Structure

```
├── Node            # Scalar value with autograd
├── Neuron          # Single neuron (weights + bias + activation)
├── Layer           # Collection of neurons
├── ANN             # Stacked layers (the full network)
├── binary_cross_entropy_loss
├── trace()         # Walks the graph, collects all nodes and edges
└── plot_grph()     # Renders the computation graph as a dark-mode SVG
```

---

## Dependencies

```
numpy
graphviz
```

No PyTorch, no TensorFlow — just math and graph traversal.

---

## Inspiration

Inspired by [Andrej Karpathy's micrograd](https://github.com/karpathy/micrograd). Built from scratch to understand what really happens under the hood when you call `.backward()`.
