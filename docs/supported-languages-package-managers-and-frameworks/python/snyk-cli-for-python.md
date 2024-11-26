# Snyk CLI for Python

## Set the Python version for CLI

To set the Python version in the CLI, add the following option to `snyk test` or `snyk monitor` with the name of the Python binary:

```sh
--command=python3
```

For details, see the options for Python Projects in the [`snyk test`](../../snyk-cli/commands/test.md) and [`snyk monitor`](../../snyk-cli/commands/monitor.md) help.

## Pip and CLI

{% hint style="info" %}
Run `pip install` before scanning with the CLI,`for` for example:

```
pip install -r requirements.txt
```
{% endhint %}

Pip `requirements.txt` files specify only top-level dependencies, not nested or transitive ones. Therefore, the full Pip Project must be installed to ensure the CLI can build a complete dependency tree.

## Poetry and CLI

To build the dependency tree for a Poetry application, Snyk uses `pyproject.toml` and `poetry.lock` files. Both files must be present for Snyk to scan Poetry dependencies and identify issues.

If no `poetry.lock` file is present; you should run `poetry lock` to generate one before scanning.

{% hint style="info" %}
[PEP 621](https://peps.python.org/pep-0621/) is a standard for defining direct dependencies in `pyproject.toml` files, which is different from how Poetry does this.

Snyk does not support PEP 621.
{% endhint %}

## Pipenv and CLI

To build the dependency tree for a Pipenv application, Snyk uses `Pipfile` and `Pipfile.lock` files. Both files must be present for Snyk to scan Pipenv dependencies and identify issues.

Run `pip install` before scanning with the CLI.

Run `pipenv install` to ensure the CLI can build an up-to-date, accurate dependency tree using `pipenv graph`.

## setup.py and CLI

To build the dependency tree, Snyk analyzes the `setup.py` file, and detects packages listed in the `install_requires` key.

This file will not be discovered automatically by the CLI. It must be specified manually using the `--file` option, for example:

```python
snyk test --file=setup.py
```

You can also convert `setup.py` to `requirements.txt` by installing the packages into a virtual environment and then running `pip freeze`.
