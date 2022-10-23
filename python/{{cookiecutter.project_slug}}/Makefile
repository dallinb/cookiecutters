all: lint test

lint:
	yamllint -s .
	bandit -qrc setup.cfg .
	flake8

test:
	pytest
