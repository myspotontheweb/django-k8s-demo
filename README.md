# django-k8s-demo
Learn how to deploy and develop a Django application on Kubernetes

## Documentation

* [Release Management](docs/releases.md)

## Software

Using [Homebrew](https://brew.sh) install CLI tooling

```bash
brew bundle install
```

## Provision a Kubernetes cluster

Using [k3d](https://k3d.io)

```bash
k3d cluster create --config k3d/config.yaml
```

Cleanup

```bash
k3d cluster delete --config k3d/config.yaml
```

## Create a new Python project

```bash
python3 -m venv .venv
source .venv/bin/activate
```