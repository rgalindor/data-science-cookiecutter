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
[![Python {{ cookiecutter.python_version }}][python-gt3-8-shield]][python-gt3-8-url] [![Code style][black-shield]][black-url] [![pre-commit][pre-commit-shield]][pre-commit-url]

## About this project

{{ cookiecutter.description }}

By: {{ cookiecutter.author }}

### Built with

 - [![Poetry][Poetry-shield]][Poetry-url] for dependency management
 - [![FastAPI][FastAPI-shield]][FastAPI-url] for API management
 - [![Docker][Docker-shield]][Docker-url] for containerization

And the basic set of tools:

 - [![Git][Git-shield]][Poetry-url] for code version control
 - [![Pdoc][Pdoc-shield]][Pdoc-url] for project documentation
 - [![Hydra][Hydra-shield]][Hydra-url] to manage configuration files
 - [![DVC][DVC-shield]][DVC-url] for data version control
 - [![Pytest][Pytest-shield]][Pytest-url] for code testing
 - [![Make][Make-shield]][Make-url] for quick builds at onboarding

### Project Structure
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
│   ├── ...
│   └── app.py                      # Main API entrypoint
├── tests                           # Tests code
├── .gitignore                      # ignore files that cannot commit to Git
├── docker-compose.yml              # local container manager deployment
├── Dockerfile                      # container recipe
├── Makefile                        # commands to set up the environment
├── .pre-commit-config.yaml         # configurations for pre-commit
├── pyproject.toml                  # Poetry dependencies
└── README.md                       # describe your project
```

### Getting started

**Before you start**

- Get sure you have `python` with a version `{{ cookiecutter.python_version }}`, if you want to start from fresh take a look at [this resource](https://wiki.python.org/moin/BeginnersGuide/Download).
- Install `poetry` by following the recommended instructions in [the official documentation](https://python-poetry.org/docs/#installation)

```bash
curl -sSL https://install.python-poetry.org | python3 -
```

To install all the dependencies of this project use

```bash
poetry install
```

## Usage

Here is described the general way to use the services in this project.

### Dependency management

To install any other dependency type

```bash
poetry add <package-name>[@<version>]
```

### Turn on the API

```bash
poetry run fastapi dev src/app.py
```

After this the swagger page will be available at [localhost:8000/docs](http://localhost:8000/docs). Note that you can set the port accordingly to your needs, however you will require another option:

```bash
poetry run uvicorn src.app:app  --reload --host=0.0.0.0 --port=8000
```

### Container usage

The project relies in the use of docker as containerization technology. So it is viable to build an image of the project suitable to contain the entire application and deployed easily with a docker engine. This project contains a `Dockerfile` structured in layers, so you can build specific target layers (`devel`, `test`, `app`) for different needs.


```bash
docker build -t devel .
```

Then you could mount volumes `data` and `models` to container folders if you want to use local folders for development.

> [!IMPORTANT]
> If you need to deploy the application you will need to use the `app` target to build an image free of local data using the classic docker build/push flow.

In addition, there is also a way to simplify the development management by using docker compose:

```bash
docker compose --profile core up -d
```

That will turn up the container using local folders mounted and every new change you add for your new feature will be use to recharge the status of the app. Then you can use `docker compose logs` to get the latest logs in the console, or `docker compose down` to turn down all the containers and clean the docker resources.

It is relevant to mention that there are three major profiles to be used with docker compose:

- `core`: Will enable local deployment of backend API service.
- `test`: Allow to run tests in the backend container.

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
