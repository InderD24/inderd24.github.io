# inderd24.github.io

This repository contains my DSCI 521 Quarto website. It includes a blog with computational posts written in R and Python.

## Requirements

Install Git, Quarto 1.10.18, uv 0.12.7, and R 4.6.1 before building.
The project uses Python 3.14, specified in `.python-version`; uv can obtain
that version if it is not already installed. You do not need to install renv
separately; the project sets it up automatically. Network access is needed to
clone the repository and install the Python and R packages.

## Build the website

Run these steps in a terminal. After step 1, stay in the top level of the
cloned repository.

### 1. Clone the repository

```bash
git clone https://github.com/InderD24/inderd24.github.io.git
cd inderd24.github.io
```

### 2. Restore the Python environment

```bash
uv sync
```

### 3. Restore the R environment

```bash
Rscript -e 'renv::restore()'
```

### 4. Render the site

```bash
uv run quarto render
```

The built website is in `docs/`. To preview the site locally, run this command
from the repository root:

```bash
uv run quarto preview
```

Quarto will open the site in your browser. Press Ctrl+C in the terminal to stop
the preview.

## Data

Both computational posts use the [Palmer Penguins
dataset](https://allisonhorst.github.io/palmerpenguins/). The Python and R
packages include the data, so rendering does not download a separate data
file. Package installation requires network access. The data source, citation, and CC0 licence are also documented in each post.

## AI Usage Statement

I used OpenAI Codex to help with issues setting up the R and Python environments on my machine, debug code and fix errors I encountered while building this website, and to help with reproducibility steps.
