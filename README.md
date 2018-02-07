# A basic setup for deploy Lambda functions with Serverless

## Installation

1. Create & Source the virtualenv

```
virtualenv .venv -p python3
source .venv/bin/activate
```

2.  Install pip tools

```
pip3 install pip-tools
```

3. Install the development requirements

```
pip-compile --output-file requirements/requirements-dev.txt requirements/requirements-dev.in

pip install -r requirements/requirements-dev.txt
```
