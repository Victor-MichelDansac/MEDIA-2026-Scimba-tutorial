# TP ScimBa (MEDIA, Toulon 2026)

This repository is a hands-on tutorial to illustrate
the PINN's approach to solving physics problems modeled with
Partial Differential Equations with the `python` programming language,
using the [ScimBa](https://www.scimba.org/) library. It consists of three notebooks:

- `1_basics.ipynb`: the basics of `scimba_jax` on two toy examples, a stationary one and a time-dependent one;
- `2a_boundary_conditions.ipynb`: strong vs. weak enforcement of boundary and initial conditions;
- `2b_models.ipynb`: defining and training a model for your own physical problem.

The notebooks at the root of this repository are the **student versions**: some
pieces of code have been removed and replaced by calls to `TODO("...")` (see the
intro cell of each notebook). The complete, filled versions are in
[`solutions/`](solutions/).

We propose `python` notebooks that can be run:
- on Google Colab,
- on your own machine.

The three tutorials use the [Jax](https://docs.jax.dev/en/latest/index.html#) backend, on top of which `ScimBa` is built, and which is introduced in the first tutorial.

## Pre-requisites

In the tutorials we assume the audience to be fluent in `python` and in `numpy`.

### Running the tutorials on Google Colab
Running the tutorial on [Google Colab](https://colab.research.google.com) requires a google account.

Download the desired notebook (`.ipynb` file) and import it in Google Colab.
You can use any of the execution environments offered.

Before importing [ScimBa](https://www.scimba.org/) just uncomment the first line of the notebook:

```python
!pip install scimba
```

to have it available in the environment.

### Running the tutorials on your own machine

Running the tutorials on your own machine requires an environment with `python>=3.11`,
and a notebook reader, as well as
the [Jax](https://docs.jax.dev/en/latest/index.html#) library (`>=0.8.1`).

The dependencies are listed in two files, depending on the package manager you use:

- [`requirements.txt`](requirements.txt) if you use `pip`;
- [`pyproject.toml`](pyproject.toml) if you use [`uv`](https://docs.astral.sh/uv/).

We explain below how to meet these requirements
with the [`uv`](https://docs.astral.sh/uv/)
package manager and with `pip`.

#### Meeting the requirements

Use either `uv` (faster) or `pip`.

In this directory, create and activate a virtual environment:

**with `uv`:**

```sh
uv venv
source .venv/bin/activate
```

**with `pip`:**

```sh
python -m venv .venv
source .venv/bin/activate
```

Then install the dependencies:

**with `uv`** (reads `pyproject.toml`):

```sh
uv sync
```

**with `pip`** (reads `requirements.txt`):

```sh
pip install -r requirements.txt
```

Sometimes it is necessary to register a python kernel linked to the environment:

```sh
uv pip install ipykernel  # or: pip install ipykernel
python -m ipykernel install --user
```

#### Run the notebooks

Preferably, just open the desired notebook (`.ipynb` file) in `visual studio code` (with the `Python` and `Jupyter` extensions installed), select the kernel corresponding to the virtual environment you created, and run the cells.

Alternatively, start jupyter lab from within the virtual environment:

```sh
jupyter-lab
```

and open the desired notebook in jupyter lab.
