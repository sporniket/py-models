# How to build and publish a python package

_See https://packaging.python.org/en/latest/tutorials/packaging-projects/#generating-distribution-archives_

## Pre-checking

* Required command : `pipx`, see [pipx homepage](https://pipx.pypa.io/stable/).
* Required python dependency manager `pdm` : `pipx install pdm`


```shell
pdm sync
```

## Run CI locally

```shell
pdm run test 
```

## Build

```shell
pdm build
```

wheel package is created inside `dist` folder.

## Publish on pypi

Check list
- [ ] Code complete and passing tests
- [ ] pyproject.toml has the right version
- [ ] Readme up to date (MUST include release notes for the release to publish)
- [ ] Tagged with git using matching version ('v' + version)

Display the token so that a copy/paste is prepared. Then use the login `__token__`, and paste the token as the password.

```shell
python3 -m twine upload --repository pypi dist/*
```
