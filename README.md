# Micrograd

A small, educational automatic-differentiation project implemented in a Jupyter notebook. It builds intuition for how gradients flow through computation graphs and how neural-network components can be assembled from scalar operations.

> **Status:** This is a learning project, not a production-ready machine-learning library.

## What you'll explore

- Numerical estimates of derivatives and how they compare with analytical gradients
- A scalar `Value` type that records operations in a computation graph
- Reverse-mode backpropagation for the implemented operations
- Graph visualization with Graphviz
- Basic neuron, layer, and multilayer-perceptron building blocks

The implementation is intentionally small so that the mechanics are visible. It does not aim to provide the broad operation coverage, performance, or numerical safeguards of a mature autodiff framework.

## Repository contents

| Path | Description |
| --- | --- |
| `Micrograd.ipynb` | Main notebook with explanations, implementation, and experiments |
| `requirements.txt` | Python dependencies for running the notebook |
| `CONTRIBUTING.md` | Guidelines for proposing improvements |

## Getting started

### Requirements

- Python 3
- Jupyter Notebook or JupyterLab
- Graphviz system executable for rendering computation graphs

### Install

Clone the repository, then install its Python dependencies:

```bash
git clone https://github.com/dev-vieester/Micrograd.git
cd Micrograd
python -m venv .venv
```

Activate the virtual environment:

```bash
# macOS / Linux
source .venv/bin/activate

# Windows PowerShell
.venv\Scripts\Activate.ps1
```

Install packages and launch the notebook:

```bash
python -m pip install -r requirements.txt
jupyter notebook Micrograd.ipynb
```

You can also open the notebook in JupyterLab or Google Colab. To render computational graphs locally, install the Graphviz system application for your operating system in addition to the Python package. See [Graphviz downloads](https://graphviz.org/download/).

## Learning path

A useful way to work through the notebook is to:

1. Evaluate and plot a simple scalar function.
2. Approximate a derivative with a small finite difference.
3. Build a computation from `Value` objects and inspect its graph.
4. Call `backward()` and compare the resulting gradients with the local derivative rules.
5. Explore how the neuron and layer abstractions compose scalar operations.

Run the notebook cells in order. The notebook is the primary interface; it is not currently packaged as an importable Python library and no automated test suite is included yet.

## Contributing

Suggestions and improvements are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) before opening a pull request. Useful next steps include adding focused tests, improving operation coverage, and making the neural-network example easier to follow.

## Acknowledgments

This project is inspired by [Andrej Karpathy's micrograd](https://github.com/karpathy/micrograd) and the broader study of automatic differentiation and deep learning.
