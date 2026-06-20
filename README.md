<div align="center">
<!-- ScalarGrad Banner -->
<svg width="680" height="260" viewBox="0 0 680 260" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <marker id="arrow" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
      <path d="M2 1L8 5L2 9" fill="none" stroke="context-stroke" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
    </marker>
    <style>
      @keyframes flow  { from{stroke-dashoffset:24} to{stroke-dashoffset:0} }
      @keyframes pulse { 0%,100%{opacity:.35} 50%{opacity:.9} }
      .fl  { stroke-dasharray:6 4; animation: flow 1.4s linear infinite; }
      .fl2 { animation-delay:.3s }  .fl3 { animation-delay:.6s }
      .fl4 { animation-delay:.9s }  .fl5 { animation-delay:.2s }  .fl6 { animation-delay:.55s }
      .op  { animation: pulse 2.2s ease-in-out infinite; }
      .op2 { animation: pulse 2.2s ease-in-out infinite .7s; }
      .op3 { animation: pulse 2.2s ease-in-out infinite 1.4s; }
    </style>
  </defs>
  <!-- grid -->
  <g opacity=".04" stroke="#888" stroke-width=".5">
    <line x1="0" y1="65"  x2="680" y2="65"/>  <line x1="0" y1="130" x2="680" y2="130"/>
    <line x1="0" y1="195" x2="680" y2="195"/>  <line x1="113" y1="0" x2="113" y2="260"/>
    <line x1="226" y1="0" x2="226" y2="260"/>  <line x1="340" y1="0" x2="340" y2="260"/>
    <line x1="454" y1="0" x2="454" y2="260"/>  <line x1="567" y1="0" x2="567" y2="260"/>
  </g>
  <!-- Input nodes -->
  <rect x="32"  y="68"  width="72" height="42" rx="7" fill="#E1F5EE" stroke="#0F6E56" stroke-width=".5"/>
  <text x="68"  y="82"  text-anchor="middle" dominant-baseline="central" font-size="12" fill="#085041" font-family="monospace">x</text>
  <text x="68"  y="98"  text-anchor="middle" dominant-baseline="central" font-size="10" fill="#1D9E75" font-family="monospace">2.0 | 0.0</text>
  <rect x="32"  y="130" width="72" height="42" rx="7" fill="#E1F5EE" stroke="#0F6E56" stroke-width=".5"/>
  <text x="68"  y="144" text-anchor="middle" dominant-baseline="central" font-size="12" fill="#085041" font-family="monospace">w</text>
  <text x="68"  y="160" text-anchor="middle" dominant-baseline="central" font-size="10" fill="#1D9E75" font-family="monospace">-0.5 | 0.0</text>
  <rect x="32"  y="192" width="72" height="42" rx="7" fill="#E1F5EE" stroke="#0F6E56" stroke-width=".5"/>
  <text x="68"  y="206" text-anchor="middle" dominant-baseline="central" font-size="12" fill="#085041" font-family="monospace">b</text>
  <text x="68"  y="222" text-anchor="middle" dominant-baseline="central" font-size="10" fill="#1D9E75" font-family="monospace">1.0 | 0.0</text>
  <!-- Edges to * -->
  <line class="fl fl2" x1="104" y1="89"  x2="160" y2="110" fill="none" stroke="#1D9E75" stroke-width="1.2" marker-end="url(#arrow)"/>
  <line class="fl fl3" x1="104" y1="151" x2="160" y2="130" fill="none" stroke="#1D9E75" stroke-width="1.2" marker-end="url(#arrow)"/>
  <!-- Op * -->
  <g class="op"><circle cx="176" cy="119" r="16" fill="none" stroke="#800080" stroke-width="1.2"/>
  <text x="176" y="119" text-anchor="middle" dominant-baseline="central" font-size="13" fill="#800080" font-family="monospace">x</text></g>
  <!-- xw node -->
  <rect x="208" y="100" width="80" height="42" rx="7" fill="#EEEDFE" stroke="#534AB7" stroke-width=".5"/>
  <text x="248" y="114" text-anchor="middle" dominant-baseline="central" font-size="12" fill="#26215C" font-family="monospace">x.w</text>
  <text x="248" y="130" text-anchor="middle" dominant-baseline="central" font-size="10" fill="#534AB7" font-family="monospace">-1.0 | 0.0</text>
  <line class="fl"     x1="192" y1="119" x2="208" y2="121" fill="none" stroke="#7F77DD" stroke-width="1.2" marker-end="url(#arrow)"/>
  <line class="fl fl4" x1="288" y1="121" x2="340" y2="121" fill="none" stroke="#7F77DD" stroke-width="1.2" marker-end="url(#arrow)"/>
  <line class="fl fl5" x1="104" y1="213" x2="340" y2="139" fill="none" stroke="#1D9E75" stroke-width="1.1" marker-end="url(#arrow)"/>
  <!-- Op + -->
  <g class="op2"><circle cx="356" cy="121" r="16" fill="none" stroke="#800080" stroke-width="1.2"/>
  <text x="356" y="121" text-anchor="middle" dominant-baseline="central" font-size="15" fill="#800080" font-family="monospace">+</text></g>
  <!-- xw+b node -->
  <rect x="386" y="100" width="88" height="42" rx="7" fill="#EEEDFE" stroke="#534AB7" stroke-width=".5"/>
  <text x="430" y="114" text-anchor="middle" dominant-baseline="central" font-size="12" fill="#26215C" font-family="monospace">x.w+b</text>
  <text x="430" y="130" text-anchor="middle" dominant-baseline="central" font-size="10" fill="#534AB7" font-family="monospace">0.0 | 0.0</text>
  <line class="fl fl2" x1="372" y1="121" x2="386" y2="121" fill="none" stroke="#7F77DD" stroke-width="1.2" marker-end="url(#arrow)"/>
  <line class="fl fl3" x1="474" y1="121" x2="524" y2="121" fill="none" stroke="#7F77DD" stroke-width="1.2" marker-end="url(#arrow)"/>
  <!-- Op tanh -->
  <g class="op3"><circle cx="540" cy="121" r="19" fill="none" stroke="#800080" stroke-width="1.2"/>
  <text x="540" y="121" text-anchor="middle" dominant-baseline="central" font-size="9" fill="#800080" font-family="monospace">tanh</text></g>
  <!-- Output node -->
  <rect x="572" y="100" width="80" height="42" rx="7" fill="#FAEEDA" stroke="#BA7517" stroke-width=".5"/>
  <text x="612" y="114" text-anchor="middle" dominant-baseline="central" font-size="12" fill="#412402" font-family="monospace">out</text>
  <text x="612" y="130" text-anchor="middle" dominant-baseline="central" font-size="10" fill="#BA7517" font-family="monospace">0.0 | 1.0</text>
  <line class="fl fl6" x1="559" y1="121" x2="572" y2="121" fill="none" stroke="#BA7517" stroke-width="1.2" marker-end="url(#arrow)"/>
  <!-- Title -->
  <text x="340" y="30" text-anchor="middle" font-size="22" font-weight="500" fill="#1a1a1a" font-family="system-ui,sans-serif">ScalarGrad</text>
  <text x="340" y="50" text-anchor="middle" font-size="12" fill="#666" font-family="system-ui,sans-serif">scalar autograd engine · neural nets · computation graph viz</text>
  <!-- Legend -->
  <rect x="32"  y="244" width="10" height="10" rx="2" fill="#1D9E75" opacity=".8"/>
  <text x="46"  y="253" font-size="10" fill="#666" font-family="system-ui,sans-serif">leaf node</text>
  <rect x="110" y="244" width="10" height="10" rx="2" fill="#7F77DD" opacity=".8"/>
  <text x="124" y="253" font-size="10" fill="#666" font-family="system-ui,sans-serif">intermediate</text>
  <rect x="218" y="244" width="10" height="10" rx="2" fill="#BA7517" opacity=".8"/>
  <text x="232" y="253" font-size="10" fill="#666" font-family="system-ui,sans-serif">output</text>
  <circle cx="305" cy="249" r="5" fill="none" stroke="#800080" stroke-width="1.1"/>
  <text x="314" y="253" font-size="10" fill="#666" font-family="system-ui,sans-serif">op node</text>
  <line x1="380" y1="249" x2="402" y2="249" stroke="#7F77DD" stroke-width="1.1" stroke-dasharray="4 3" marker-end="url(#arrow)"/>
  <text x="407" y="253" font-size="10" fill="#666" font-family="system-ui,sans-serif">forward pass</text>
</svg>
</div>

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
