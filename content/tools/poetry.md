---
title: "Poetry"
tags:
-   tools
-   python
---

## Install
`pip install poetry`

## Setting up new project
`poetry new poetry-demo`

Creates the following content:

```
poetry-demo
├── pyproject.toml
├── README.md
├── poetry_demo
│   └── __init__.py
└── tests
    └── __init__.py
```

## Initialise pre-existing project
`poetry init`

## Poetry venvs in project itself
`poetry config virtualenvs.in-project true`

## Install dependencies
`poetry install`
Also makes it possible to run the program with a start script

## Activate virtual env in current shell
`poetry shell`

## Add dependency
```
poetry shell
poetry add textual
poetry add textual-dev --group dev
```

