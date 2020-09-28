# Project X - University of Alberta

## Setup
First install [Anaconda](https://www.anaconda.com/products/individual), a Python distribution / package manager.

The first command here creates a new conda environment named `projectx` and installs our base packages. 

```shell script
# create the conda environment
$ conda env create -n projectx -f env/base.yml

# activate the conda environment
$ conda activate projectx

# to deactivate the conda environment
$ conda deactivate

# update the conda environment with an environment yml file
$ conda env update -n projectx -f <path to .yml file>

# to remove the conda environment
$ conda env remove -n projectx
```

If you need a python package that isn't in the `base.yml` file, add it there and update the environment.

#### CPU / GPU specific libraries

Some libraries (mainly deep learning libraries like PyTorch and Tensorflow) must be installed differently if you have a CUDA-capable GPU, these should be installed separately from the `base.yml` file.

```shell script
#--- PyTorch Installation ---#

# CPU only
$ conda env update -n projectx -f env/torch-cpu.yml

# GPU
$ conda env update -n projectx -f env/torch-gpu.yml
```

## Code Style
Before you push any Python code, format it using `black`. If you make a pull request with unformatted code a check will fail on the PR.

```shell script
$ black .
```

## Git Workflow
Don't push directly to master, instead work on a separate branch and when it's ready you can open a pull request. If the changes are non-trivial somebody should review and approve the pull request before you merge it.

## Project Structure
```
.
├── .github
|   └── workflows   github actions
├── src             source code
├── notebooks       jupyter notebooks
├── data            data (large data should be hosted in the google drive and gitignored)
├── models          trained models (again, large files in google drive, not on the repo)
├── papers          LaTeX files, bibliographies, etc.
└── env             conda environment files
```
Try to structure things logically within each directory.
