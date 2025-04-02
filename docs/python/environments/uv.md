# uv

## Start Project

```bash
uv init projectName
```

## Manage Pythons

### Install Latest Version

```bash
uv python install
```

```bash
uv python install 3.12
uv python install 3.11 3.12
uv python install pypy@3.10
uv python install --reinstall
uv python list
```

### Pin Dependencies

```base
uv add <<package_name>>
```

```base
uv remove <<package_name>>
```

### Running Scripts

Running scripts without explicity activating venv.

```bash
uv run example.py
uv run --no-project example.py
```

### Create Environment

```bash
uv venv
```

```bash
uv venv <<someEnvionmentName>>
```

```bash
uv venv --python 3.13
```

```bash
uv venv --python 3.12 <<someEnvironmentName>>
```

### Activate Environment

```bash
source .venv/bin/activate
```

### Deactivate Environment

```bash
deactivate
```

### Pinning Dependencies

```bash
uv pip install ruff
```

```bash
uv add -r requirements/development.txt --group development
```

```bash
uv pip install -r pyproject.toml --extra development
```

```bash
uv pip compile requirements/development.in > requirements/development.txt
```

## Python Environment Discovery

uv will search for a virtual environment in the following order:

1. An activated virtual environment based on:

   1. VIRTUAL_ENV environment variable.
   1. CONDA_PREFIX environment variable.

1. A virtual environment at .venv:

   1. in the current directory.
   1. in the nearest parent directory.

1. uv will prompt the user to create one in the current directory via uv venv.
1. --system flag will search for the installed system Python version.

## References

- [Python environments](https://docs.astral.sh/uv/pip/environments/#python-environments)
