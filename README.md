# Micrograd

A small, educational automatic differentiation project built in a Jupyter notebook. This repository explores the core ideas behind modern deep learning frameworks by implementing a minimal `Value` class, reverse-mode autodiff, and a tiny neural network from scratch.

The notebook is inspired by the original `micrograd` project by Andrej Karpathy and is designed to help you understand how frameworks like PyTorch compute gradients and train models.

## What is included

- A lightweight `Value` class that supports:
  - scalar arithmetic (`+`, `*`)
  - basic activation functions such as `tanh`
  - gradient accumulation via backpropagation
- Visualization of computational graphs using `graphviz`
- Simple examples showing numerical differentiation and gradient behavior
- A tiny neural network implementation using custom layers and neurons

## Repository contents

- `Micrograd.ipynb` — the main notebook containing the implementation and experiments

## Features

- Understand automatic differentiation step by step
- See how gradients flow through a computation graph
- Build intuition for neural network training without relying on a full framework
- Learn foundational concepts behind modern ML libraries

## Getting started

### Prerequisites

Make sure you have Python 3 installed.

### Install dependencies

```bash
pip install numpy matplotlib graphviz jupyter
```

If `graphviz` is not available on your system, you may also need to install the Graphviz binary from:

https://graphviz.org/download/

### Run the notebook

```bash
jupyter notebook Micrograd.ipynb
```

Or with JupyterLab:

```bash
jupyter lab
```

## Example concepts covered

The notebook walks through:

- evaluating scalar functions
- approximating derivatives numerically
- building a computation graph
- implementing backpropagation manually
- training a small network with gradient descent ideas

## Project goals

This project is primarily for learning and experimentation. It is ideal for:

- understanding how autodiff works under the hood
- studying the math behind gradient descent
- exploring computational graphs visually
- building a foundation for larger ML frameworks

## Notes

This repository is intentionally minimal and educational rather than production-oriented. It is meant to help you understand the mechanics behind deep learning systems by building them directly.

## License

This project does not currently specify a license. If you intend to share or reuse it publicly, consider adding one such as MIT.

## Inspired by

- Andrej Karpathy's `micrograd`
- The broader literature on automatic differentiation and deep learning

## Contributing

If you'd like to extend this project, you could consider adding:

- a `requirements.txt` file
- a proper Python package structure
- unit tests for the `Value` class
- additional activation functions and optimizers
- a clearer exportable script version outside the notebook

## Quick example

```python
from math import exp

class Value:
    def __init__(self, data, _children=(), _op=''):
        self.data = data
        self.grad = 0.0
        self._backward = lambda: None
        self._prev = set(_children)
        self._op = _op

    def __add__(self, other):
        out = Value(self.data + other.data, (self, other), '+')
        def _backward():
            self.grad += 1.0 * out.grad
            other.grad += 1.0 * out.grad
        out._backward = _backward
        return out

    def __mul__(self, other):
        out = Value(self.data * other.data, (self, other), '*')
        def _backward():
            self.grad += other.data * out.grad
            other.grad += self.data * out.grad
        out._backward = _backward
        return out
```

This is the core idea behind the notebook: each operation stores the local derivative rule so the full gradient can be computed by walking the graph backward.
