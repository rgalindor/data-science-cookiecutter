.PHONY: tests docs env init

init: 
	@echo "Initializing Git..."
	git init
	@echo "Installing dependencies..."
	poetry install
	poetry run pre-commit install

dependencies:
	@echo "Updating dependencies"
	poetry install

env: dependencies
	@echo "Activating virtual environment..."
	poetry shell

tests:
	poetry run pytest .

docs:
	@echo "Save documentation to docs... "
	poetry run pdoc src -o docs --force
	@echo "View API documentation... "
	poetry run pdoc src --http localhost:8080

api: src/app.py
	@echo "Serving local API"
	poetry run fastapi dev src/app.py
