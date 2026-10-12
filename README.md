# 2026-10-12-hsf-india-tutorial-delhi

Python, array-oriented programming, ragged arrays, and scaling: a four-lesson tutorial for the HSF-India school in Delhi, October 2026.

Each of the 4 lessons has

* `lecture-slides.ipynb`: what the instructor presents
* `lecture-workbook.ipynb`: what you run to follow along
* one or two projects with solutions: open the project when the lecture is done, and do not peek at the solutions until you are done.

Lesson 1 only has a physics problem. Lessons 2, 3, and 4 each have a physics problem (Higgs hunting) and a non-physics problem. Choose the one that interests you!

Lesson 3 project 1 streams a 611 MB Parquet file from Zenodo, one row group at a time. The other notebooks only use the files in `data/`.

## Option 0: in your browser (no installation)

Open <https://henryiii.github.io/2026-10-12-hsf-india-tutorial-delhi/lab/index.html>. This runs Python in your browser with [Pyodide](https://pyodide.org) and [JupyterLite](https://jupyterlite.readthedocs.io). Packages that Pyodide does not include need `%pip install` first (for example `%pip install vector hist hepunits particle uproot`). Numba, JAX, pybind11, and `dask.distributed` do not work in the browser, so use another option for lesson 4.

To build it locally, run `uvx nox -s pyodide -- serve`.

## Option 1: JupyterHub (no installation)

Start a JupyterHub session with no GPU:

<https://binderhub.ssl-hep.org/v2/gh/research-software-collaborations/courses-hsf-india-june2025/lite>

<p align="center"><img src="https://github.com/jpivarski-talks/2024-05-22-hsf-india-tutorial-delhi/assets/1852447/9f57768b-7d3d-4b74-8364-c066fe352c39" width="75%"></p>

Bring up a terminal by pressing the "Terminal" button:

<p align="center"><img src="https://github.com/jpivarski-talks/2024-05-22-hsf-india-tutorial-delhi/assets/1852447/9efd21b4-1cd7-45b7-80d0-a20bb0c36ac4" width="75%"></p>

In that terminal, clone this repository with

```bash
git clone https://github.com/henryiii/2026-10-12-hsf-india-tutorial-delhi.git
```

<p align="center"><img src="https://github.com/jpivarski-talks/2024-05-22-hsf-india-tutorial-delhi/assets/1852447/89b5625b-c1db-44f7-8ce7-774ed592580e" width="75%"></p>

Now there is a `2026-10-12-hsf-india-tutorial-delhi` directory that you can double-click.

<p align="center"><img src="https://github.com/jpivarski-talks/2024-05-22-hsf-india-tutorial-delhi/assets/1852447/32497618-3df3-4718-b643-fa38d05d56fb" width="75%"></p>

<p align="center"><img src="https://github.com/jpivarski-talks/2024-05-22-hsf-india-tutorial-delhi/assets/1852447/9d8df96b-a463-4702-9e40-c003dc5f8694" width="75%"></p>

## Option 2: run locally with pixi (recommended)

Install [pixi](https://pixi.sh/latest/installation/), then:

```bash
git clone https://github.com/henryiii/2026-10-12-hsf-india-tutorial-delhi.git
cd 2026-10-12-hsf-india-tutorial-delhi
pixi run start
```

This installs everything (including a C++ compiler for lesson 4) and starts JupyterLab.

## Option 3: run locally with conda

Install [Miniforge](https://conda-forge.org/download/), then:

```bash
conda env create -f environment.yml
conda activate array-oriented-programming
dot -c   # registers graphviz plugins, needed once for lesson 4
jupyter lab
```
