# Simple KRR Dashboard Helm Chart

> [!NOTE]
> This project is not affiliated with [robusta-dev/krr](https://github.com/robusta-dev/krr).

[Simple KRR Dashboard](https://github.com/devops-ia/simple-krr-dashboard) is a product that helps show data from [robusta-dev/krr](https://github.com/robusta-dev/robusta-krr).

## Usage

Charts are available in:

* [Chart Repository](https://helm.sh/docs/topics/chart_repository/)
* [OCI Artifacts](https://helm.sh/docs/topics/registries/)

### Chart Repository

#### Add repository

```console
helm repo add simple-krr-dashboard https://devops-ia.github.io/helm-simple-krr-dashboard
helm repo update
```

#### Install Helm chart

```console
helm install [RELEASE_NAME] simple-krr-dashboard/simple-krr-dashboard
```

This install all the Kubernetes components associated with the chart and creates the release.

_See [helm install](https://helm.sh/docs/helm/helm_install/) for command documentation._

### OCI Registry

Charts are also available in OCI format. The list of available charts can be found [here](https://github.com/devops-ia/helm-simple-krr-dashboard/pkgs/container/helm-simple-krr-dashboard%2Fsimple-krr-dashboard).

#### Install Helm chart

```console
helm install [RELEASE_NAME] oci://ghcr.io/devops-ia/helm-simple-krr-dashboard/simple-krr-dashboard --version=[version]
```

## Simple KRR Dashboard chart

Can be found in [simple-krr-dashboard chart](charts/simple-krr-dashboard).
