<!-- PROJECT SHIELDS -->

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]

# Data Science Cookiecutter Template
[![Python >=3.8][python-gt3-8-shield]][python-gt3-8-url] [![Code style][black-shield]][black-url] [![pre-commit][pre-commit-shield]][pre-commit-url]

This repo is based on a nice template first presented in the [Github repo for DataScience cookie cutter ](https://github.com/khuyentran1401/data-science-template/blob/dvc-poetry/README.md) by [Khuyen Tran](https://github.com/khuyentran1401)

This repository provides a template that incorporates best practices to create a maintainable and reproducible data science project.

## Tools used in this project
 - [![Poetry][Poetry-shield]][Poetry-url] for dependency management
 - [![Git][Git-shield]][Poetry-url] for Code Version Control
 - [![Pdoc][Pdoc-shield]][Pdoc-url] for project documentation
 - [![Hydra][Hydra-shield]][Hydra-url] to manage configuration files
 - [![DVC][DVC-shield]][DVC-url] for Data Version Control
 - [![Pytest][Pytest-shield]][Pytest-url] for Code testing
 - [![Make][Make-shield]][Make-url] for quick builds at onboarding
 
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


## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are greatly appreciated. Don't forget to give the project a star!

If you have a suggestion that would make this better, please **fork the repo** and **create a pull request**. You can also simply open an issue with the tag "enhancement". Please follow the following guidelines when contributing:

1. **Create your feature branch:** Use the appropriate branch naming convention based on the type of change you are making:

- For new development, use: `feat/commit_name`
- For bug fixes, use: `fix/commit_name`
- For documentation improvements, use: `doc/commit_name`

Example:

```bash
git checkout -b feat/add-an-awesome-new-feature
```
2. **Commit your changes:** Make sure your commit message is clear and follows conventional commit guidelines:

```bash
git commit -m 'feat: add a fantastic new feature'
```
3. **Push to the branch:**

```bash
git push origin feat/add-an-awesome-new-feature
```
4. **Open a Pull Request:** After pushing your branch, open a Pull Request (PR) and ensure to follow the [guidelines on conventional commits](https://www.conventionalcommits.org/en/v1.0.0/)


Thanks again!

### Top contributors:

<a href="https://github.com/othneildrew/Best-README-Template/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=rgalindor/data-science-cookiecutter" alt="contrib.rocks image" />
</a>


<!-- CONTACT -->
## Contact

Roberto Galindo Ramírez - rgalindo.biocomputo@gmail.com.com

[![LinkedIn][linkedin-shield]][linkedin-url]

Project Link: [https://github.com/rgalindor/data-science-cookiecutter](https://github.com/rgalindor/data-science-cookiecutter)



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

[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/roberto-galindo-ram%C3%ADrez-034a5451
<!-- TOOLS -->
[python-gt3-8-shield]: https://img.shields.io/badge/python->=3.8-blue.svg?logo=python&logoColor=white
[python-gt3-8-url]: https://www.python.org/downloads/release/python-38/
[black-shield]: https://img.shields.io/badge/code%20style-black-000000.svg
[black-url]: https://github.com/psf/black
[pre-commit-shield]: https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit
[pre-commit-url]: https://github.com/pre-commit/pre-commit
[Poetry-shield]: https://img.shields.io/badge/Poetry-444444.svg?style=for-the-badge&logo=poetry
[Poetry-url]: https://python-poetry.org
[Docker-shield]: https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white
[Docker-url]: https://python-poetry.org
[Llama-index-shield]: https://img.shields.io/badge/-%F0%9F%A6%99%20%20%20%20%20llama--index%20-green?style=for-the-badge
[Llama-url]: https://docs.llamaindex.ai/en/stable
[FastAPI-shield]: https://img.shields.io/badge/FastAPI-009485.svg?style=for-the-badge&logo=fastapi&logoColor=white
[FastAPI-url]: https://fastapi.tiangolo.com
[Git-shield]: https://img.shields.io/badge/Git-444444.svg?style=for-the-badge&logo=git
[Git-url]: https://git-scm.com/
[Pdoc-shield]: https://img.shields.io/badge/pdoc-229944.svg?style=for-the-badge&logo=python&logoColor=yellow
[Pdoc-url]: https://pdoc3.github.io/pdoc/doc/pdoc/#gsc.tab=0
[Hydra-shield]: https://img.shields.io/badge/Hydra-54c7ec.svg?style=for-the-badge&logo=python
[Hydra-url]: https://hydra.cc/docs/intro/
[DVC-shield]: https://img.shields.io/badge/DVC-444444.svg?style=for-the-badge&logo=dvc
[DVC-url]: https://dvc.org/doc
[Pytest-shield]: https://img.shields.io/badge/Pytest-444444.svg?style=for-the-badge&logo=pytest
[Pytest-url]: https://docs.pytest.org/en/stable/
[Make-shield]: https://img.shields.io/badge/Makefile-a32d2a.svg?style=for-the-badge&logo=gnu
[Make-url]: https://github.com/mirror/make
