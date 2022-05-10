# Documentation of pnp-zone

This is the documentation of [pnp-zone](https://github.com/pnp-zone/pnp-zone). It uses `mkdocs` with the beautiful `material` theme.

## Changes

In order to make changes and build the documentation following requirements are necessary:

- python
- python-pip

as well as the python modules:

```bash
python -m pip install -r requirements.txt
```

To build the documentation run:
```bash
mkdocs build
```

To spin up a self-refreshing development server:
```bash
mkdocs server -a bind_addr:port
```
