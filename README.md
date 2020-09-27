# Project X - University of Alberta

## Setup
First install [Anaconda](https://www.anaconda.com/products/individual), a Python distribution / package manager.

These commands create a new conda environment named `projectx` and install our required packages. 

```shell script
# create the conda environment
$ conda env create -f environment.yml

# activate the conda environment
$ conda activate projectx

# deactivate the conda environment
$ conda deactivate

# update the conda environment
$ conda env update --name projectx -f environment.yml
```

If you need a python package that isn't in the `environment.yml` file, add it there and update the environment.

## Code Style
Before you push any Python code, format it using `black`. If you make a pull request with unformatted code a check will fail on the PR.

```shell script
$ black .
```

## Git Workflow
Don't push directly to master, instead work on a separate branch and when it's ready you can open a pull request. If the changes are non-trivial somebody should review and approve the pull request before you merge it.

## Project Structure
Code goes in `/src`, notebooks in `/notebooks`, data in `/data`, models in `/models`. 

Try to structure things logically within each directory.
