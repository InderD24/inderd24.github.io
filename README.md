# Indervir Dhillon's website

This repository contains my DSCI 521 Quarto website. It includes a blog with computational posts written in R and Python.

## Requirements

Install Git, Quarto 1.10.18, uv 0.12.7, and R 4.6.1 before building.
The project uses Python 3.14, specified in `.python-version`; uv can obtain
that version if it is not already installed. Network access is needed to install the Python and R packages.


## Build the website

Run these commands in a terminal. After `cd`, run every command from the
top level of the cloned repository, where `_quarto.yml` is located:

```bash
git clone https://github.com/InderD24/inderd24.github.io.git
cd inderd24.github.io
uv sync --frozen
Rscript -e 'renv::restore(prompt = FALSE)'
uv run quarto render
```

The built website is in `docs/`. To view it locally, run this command from the repository root:

```bash
uv run python -m http.server 8000 --directory docs
```

Open http://localhost:8000 in a browser. Press Ctrl+C in the terminal to
stop the server.

## Data

Both computational posts use the [Palmer Penguins
dataset](https://allisonhorst.github.io/palmerpenguins/). The Python and R
packages include the data, so rendering does not download a separate data
file. Package installation requires network access. The data source, citation, and CC0 licence are also documented in each post.

## AI Usage Statement
I used OpenAI Codex to help with issues setting up the R and Python environments on my machine. I also used AI to debug code and fix errors I encountered while building this website.
