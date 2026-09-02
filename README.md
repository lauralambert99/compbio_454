# Computing in Biotechnology

Course materials. Everything here is free and open-source; no accounts required beyond a
Google account if you choose to work in Colab.

## Getting the files

Click the green **Code** button above, then **Download ZIP**. Unzip it somewhere you
will find again — Documents is good, Downloads is not.

Keep the folder structure intact. The notebook looks for `fixtures/` sitting beside it.

## Setting up (once, at the start of semester)

You need **Miniforge** installed first: https://conda-forge.org/download/

Then open a terminal — **Miniforge Prompt** on Windows, **Terminal** on macOS — navigate
into this folder, and run:

**macOS**
```
conda env create -f setup/environment.yml
conda activate compbiotech
jupyter lab
```

**Windows**
```
conda env create -f setup/environment-windows.yml
conda activate compbiotech
jupyter lab
```

The first command takes a few minutes and downloads a lot. "Solving environment" looks
stuck but is not.

## Every week after that

Creating the environment happens **once**. Activating happens **every time you open a
new terminal**:

```
conda activate compbiotech
jupyter lab
```

Your prompt should show `(compbiotech)` once activated. If it does not, nothing else
will work properly.

## Checking you are in the right Python

Before running a notebook, run this in a cell:

```python
import sys
print(sys.executable)
```

The path must contain `compbiotech`. If it does not, quit Jupyter (Ctrl+C in the
terminal), activate the environment, and start `jupyter lab` again.

## Running in Google Colab instead

You can open any notebook in Colab without installing anything. See the link in each
week's section below. If you use Colab, the notebook installs what it needs itself.

Windows users: Weeks 8, 9, 11 and 12 need tools that have no Windows build, so use
Colab for those four. Everything else runs locally.

## Weeks

### Week 1 — Identifiers, and why they do not match

`week01_identifiers_student.ipynb`

What a protein is, as far as a database is concerned: accessions, entry names, evidence
codes, and why the same protein has several different names in several different places.

## Troubleshooting

**`conda: command not found`** — Windows: use Miniforge Prompt, not Command Prompt.
macOS: run `conda init zsh`, then close and reopen Terminal.

**`ModuleNotFoundError: No module named 'Bio'`** — you are in the wrong Python. Check
for `(compbiotech)` in your prompt.

**`FileNotFoundError: dhfr_ecoli.fasta not found`** — the `fixtures` folder is not next
to the notebook. Re-download the ZIP and keep the structure.

**Never `pip install vina`** — on macOS and Windows there is no wheel, so pip tries to
compile it and fails on a confusing Boost error. It comes from conda on macOS, and on
Windows it does not exist at all.
