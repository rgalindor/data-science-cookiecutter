FROM python:{{ cookiecutter.python_image_version }} AS base

# https://python-poetry.org/docs#ci-recommendations
ENV POETRY_VERSION=1.5.1 \
    POETRY_HOME=/opt/poetry \
    POETRY_VENV=/opt/poetry-venv \
    APP_HOME=/app

ENV PATH="${POETRY_HOME}/bin:${PATH}"
ENV PATH="${VENV_PATH}/bin:${PATH}"
WORKDIR ${APP_HOME}
ENV VENV_PATH=${POETRY_VENV}
# Add Poetry to PATH
ENV PATH="${PATH}:${POETRY_VENV}/bin"

# Tell Poetry where to place its cache and virtual environment
ENV POETRY_CACHE_DIR=/opt/.cache


# Install main OS packages
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
    wget \
    curl \
    gcc \
    make \
    openssl


RUN python3 -m venv ${POETRY_VENV} \
    && ${POETRY_VENV}/bin/pip install poetry==${POETRY_VERSION}

# ---- build ----

FROM base AS build

COPY --from=base ${POETRY_VENV} ${POETRY_VENV}
COPY poetry.lock pyproject.toml ${APP_HOME}
RUN poetry check

# ---- app ----

FROM build AS app

COPY --from=build ${POETRY_VENV} ${POETRY_VENV}
COPY --from=build ${APP_HOME} ${APP_HOME}

RUN poetry install --no-interaction --no-cache --only main

# Copy Application
COPY src ${APP_HOME}/src

RUN mkdir -p ${APP_HOME}/data/
RUN mkdir -p ${APP_HOME}/models/

EXPOSE 8001
CMD [ "poetry", "run" , "fastapi", "run", "src/app.py", "--port",  "8001" ]


# ---- test ----
FROM build AS test

COPY --from=build ${POETRY_VENV} ${POETRY_VENV}
COPY --from=build ${APP_HOME} ${APP_HOME}
RUN poetry install --no-interaction --no-cache --only main,test


# ---- devel ----

FROM build AS devel

COPY --from=build ${POETRY_VENV} ${POETRY_VENV}
COPY --from=build ${APP_HOME} ${APP_HOME}

RUN poetry install --no-interaction --no-cache

EXPOSE {{ cookiecutter.docker_dev_port }}
CMD [ "poetry", "run" , "fastapi", "dev", "src/app.py",   "--port",  "{{ cookiecutter.docker_dev_port }}" ]

