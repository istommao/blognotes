# Python开发环境搭建

## pyenv安装

- https://github.com/pyenv/pyenv

```shell
pyenv install 3.6.2
```

## pipenv安装

- https://github.com/pypa/pipenv

```shell
brew install pipenv
```


## pre-commit

- https://github.com/pre-commit/pre-commit

`config .pre-commit-config.yaml`

```shell
# .pre-commit-config.yaml
repos:
-   repo: https://github.com/pre-commit/pre-commit-hooks
    rev: v1.4.0
    hooks:
    -   id: trailing-whitespace
        exclude: '^docs/'
    -   id: end-of-file-fixer
        exclude: '^docs/'
    -   id: autopep8-wrapper
        exclude: \/migrations\/
    -   id: check-docstring-first
    -   id: check-json
    -   id: check-added-large-files
    -   id: check-yaml
    -   id: debug-statements
    -   id: requirements-txt-fixer
-   repo: https://github.com/pre-commit/pre-commit
    rev: v1.11.0
    hooks:
    -   id: validate_manifest
-   repo: local
    hooks:
    -   id: pylint
        name: pylint
        entry: pylint
        language: system
        files: \.py$
        exclude: '((migrations)/|((docs)/)'
        args: [--rcfile=.pylintrc, --load-plugins=pylint_django]
```

```shell
# .pre-commit-hooks.yaml
-   id: validate_manifest
    name: Validate Pre-Commit Manifest
    description: This validator validates a pre-commit hooks manifest file
    entry: pre-commit-validate-manifest
    language: python
    files: ^(\.pre-commit-hooks\.yaml|hooks\.yaml)$
```

```shell
pipenv install pre-commit

pre-commit
pre-commit install
```
