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

4. Install docker-machine & create a main container

```
$ brew install docker-machine
$ docker-machine create main
```

## Deployments

1. Make sure docker is started and env variables are set:

```
$ docker-machine start main
$ eval $(docker-machine env main)
```

2. Update the `requirements.txt` file:

```
$ pip-compile --output-file requirements.txt requirements/requirements.in
```

3. Deploy

```
$ serverless deploy --stage staging
```
