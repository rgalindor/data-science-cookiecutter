<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
-->
# {{ cookiecutter.project_title }}

{{ cookiecutter.description }}

By: {{ cookiecutter.author }}

## Project Structure
```bash
.
├── config
│   ├── main.yaml                   # Main configuration file
│   ├── model                       # Configurations for training model
│   └── process                     # Configurations for processing data
├── data
│   ├── final                       # data after training the model
│   ├── processed                   # data after processing
│   ├── raw                         # raw data
│   └── raw.dvc                     # DVC file
├── docs                            # documentation for your project
├── models                          # Models folder
├── notebooks                       # Notebooks folder
├── src                             # Main source code
├── tests                           # Tests code
├── .gitignore                      # ignore files that cannot commit to Git
├── Makefile                        # commands to set up the environment
├── .pre-commit-config.yaml         # configurations for pre-commit
├── pyproject.toml                  # Poetry dependencies
└── README.md                       # describe your project
```

### Getting started

**Before you start**

- Get sure you have `python` with a version `>=3.8`, if you want to start from fresh take a look at [this resource](https://wiki.python.org/moin/BeginnersGuide/Download).
- Install `poetry` by following the recommended instructions in [the official documentation](https://python-poetry.org/docs/#installation)

```bash
curl -sSL https://install.python-poetry.org | python3 -
```

To install all the dependencies of this project use

```bash
poetry install
```

To install any other dependency type

```bash
poetry add <package-name>[@<version>]
```



## Contact info

{{ cookiecutter.author }}


<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
<!-- PRIVATE REPOS SHIELDS-->
[contributors-shield]: https://img.shields.io/badge/contributors-666666?style=for-the-badge
[forks-shield]: https://img.shields.io/badge/forks-666666?style=for-the-badge
[stars-shield]: https://img.shields.io/badge/stars-666666?style=for-the-badge
[issues-shield]: https://img.shields.io/badge/issues-666666?style=for-the-badge
<!-- PUBLIC REPOS SHIELDS-->
<!-- [contributors-shield]: https://img.shields.io/github/contributors/github_user/github_repo.svg?style=for-the-badge -->
<!-- [forks-shield]: https://img.shields.io/github/forks/github_user/github_repo.svg?style=for-the-badge -->
<!-- [stars-shield]: https://img.shields.io/github/stars/github_user/github_repo.svg?style=for-the-badge -->
<!-- [issues-shield]: https://img.shields.io/github/issues/github_user/github_repo.svg?style=for-the-badge -->
<!-- LINKS -->
[contributors-url]: https://github.com/github_user/github_repo/graphs/contributors
[forks-url]: https://github.com/github_user/github_repo/network/members
[stars-url]: https://github.com/github_user/github_repo/stargazers
[issues-url]: https://github.com/github_user/github_repo/issues
