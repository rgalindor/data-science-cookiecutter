<!-- PROJECT SHIELDS -->

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]

# Data Science Cookie Cutter

This repo is based on a nice template first presented in the [Github repo for DataScience cookie cutter ](https://github.com/khuyentran1401/data-science-template/blob/dvc-poetry/README.md) by [Khuyen Tran](https://github.com/khuyentran1401)

This repository provides a template that incorporates best practices to create a maintainable and reproducible data science project.

## Tools used in this project
 - [poetry](#) for dependency management
 - [git](#) for Code Version Control
 - [pdoc](#) for project documentation
 - [hydra](#) to manage configuration files
 - [DVC](#) for Data Version Control
 
 ## Project Structure

```bash
.
├── config                      
│   ├── main.yaml                   # Main configuration file
│   ├── model                       # Configurations for training model
│   │   ├── model_m.yaml            # First variation of parameters to train model
│   │   └── model_n.yaml            # Second variation of parameters to train model
│   └── process                     # Configurations for processing data
│       ├── process_a.yaml          # First variation of parameters to process data
│       └── process_b.yaml          # Second variation of parameters to process data
├── data            
│   ├── final                       # data after training the model
│   ├── processed                   # data after processing
│   ├── raw                         # raw data
│   └── raw.dvc                     # DVC file of data/raw
├── docs                            # documentation for your project
├── models                          # store models
├── notebooks                       # store notebooks
├── src                             # store source code
│   ├── __init__.py                 # make src a Python module 
│   ├── process.py                  # process data before training model
│   └── train_model.py              # train model
├── tests                           # store tests
│   ├── __init__.py                 # make tests a Python module
│   ├── test_process.py             # test functions for process.py
│   └── test_train_model.py         # test functions for train_model.py
├── .gitignore                      # ignore files that cannot commit to Git
├── .pre-commit-config.yaml         # configurations for pre-commit
├── Makefile                        # store useful commands to set up the environment
├── pyproject.toml                  # dependencies for poetry
└── README.md                       # describe your project
```

## How to use this project

Install Cookiecutter using an environment:
```bash
pip install cookiecutter
```

```bash
conda install cookiecutter
```

```bash
poetry install cookiecutter
```

Create a project based on the template:
```bash
cookiecutter https://github.com/rgalindor/data-science-cookiecutter --checkout main
```

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
<!-- [contributors-shield]: https://img.shields.io/badge/contributors-666666?style=for-the-badge -->
[contributors-shield]: https://img.shields.io/github/contributors/rgalindor/data-science-cookiecutter.svg?style=for-the-badge
[contributors-url]: https://github.com/rgalindor/data-science-cookiecutter/graphs/contributors
<!-- [forks-shield]: https://img.shields.io/badge/forks-666666?style=for-the-badge -->
[forks-shield]: https://img.shields.io/github/forks/rgalindor/data-science-cookiecutter.svg?style=for-the-badge
[forks-url]: https://github.com/rgalindor/data-science-cookiecutter/network/members
<!-- [stars-shield]: https://img.shields.io/badge/stars-666666?style=for-the-badge -->
[stars-shield]: https://img.shields.io/github/stars/rgalindor/data-science-cookiecutter.svg?style=for-the-badge
[stars-url]: https://github.com/rgalindor/data-science-cookiecutter/stargazers
<!-- [issues-shield]: https://img.shields.io/badge/issues-666666?style=for-the-badge -->
[issues-shield]: https://img.shields.io/github/issues/rgalindor/data-science-cookiecutter.svg?style=for-the-badge
[issues-url]: https://github.com/rgalindor/data-science-cookiecutter/issues
