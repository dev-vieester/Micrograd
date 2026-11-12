# Contributing

Thanks for taking an interest in improving Micrograd. The project is a small educational notebook, so changes should make the concepts clearer and keep the setup lightweight.

## Before you start

- Check existing issues and pull requests to avoid duplicating work.
- For a substantial change, open an issue first to discuss the approach.
- Keep changes focused and explain the learning benefit in your pull request.

## Working on the notebook

1. Create a branch for your change.
2. Install dependencies using `python -m pip install -r requirements.txt`.
3. Open `Micrograd.ipynb` in Jupyter and run the relevant cells from top to bottom.
4. Check that code cells run without errors and that plots or Graphviz visualizations render when relevant.
5. Keep explanations concise and make sure new concepts are introduced before they are used.

If you add dependencies, update `requirements.txt` and explain why they are needed. Avoid committing temporary notebook checkpoints or local environment files.

## Pull requests

Please include:

- A clear summary of the change and its motivation.
- Any relevant issue number.
- The steps you used to verify the notebook.
- Screenshots or outputs when they help explain a visualization or behavior change.

There is no automated test suite yet, so please state explicitly which notebook cells or examples you ran. Constructive, respectful discussion is expected.
