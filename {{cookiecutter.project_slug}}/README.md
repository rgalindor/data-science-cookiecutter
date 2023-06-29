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
├── .gitignore                      # ignore files that cannot commit to Git
├── Makefile                        # commands to set up the environment
├── models                          # Models folder
├── notebooks                       # Notebooks folder
├── .pre-commit-config.yaml         # configurations for pre-commit
├── pyproject.toml                  # Poetry dependencies
├── README.md                       
├── src                             # Main source code
└── tests                           # Tests code
```

### Getting started

**Before you start**

- Get sure you have `python` with a version `>=3.8`, if you want to start from fresh take a look at [this resource](https://wiki.python.org/moin/BeginnersGuide/Download).
- Install `poetry` by following the reccomended instructions in [the oficial documentation](https://python-poetry.org/docs/#installation)

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