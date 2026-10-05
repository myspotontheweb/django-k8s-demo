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

# Install the cloudnativepg operator
helm repo add cnpg https://cloudnative-pg.github.io/charts
helm repo update

helm upgrade cnpg cnpg/cloudnative-pg --install --namespace cnpg-system --create-namespace 
```

Setup a development namespace and database

```bash
kubectl create ns dev-01
kubectl apply -f manifests/db.yaml -n dev-01
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