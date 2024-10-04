```
⚠️ ARCHIVE NOTICE ⚠️

This repository has been archived and is no longer actively maintained. 
The code and documentation are provided as-is, without warranty of any kind.
```

# Open Deploy

Open Deploy is an open-source enterprise software delivery platform designed for managing updates in private cloud and on-premises environments. It provides a robust solution for packaging, distributing, and managing software updates across multiple deployment scenarios, including Kubernetes clusters using Helm charts.

## Features

- **Update Packaging**: Securely package your software updates, including all dependencies.
- **Flexible Distribution**: Deploy updates to various environments, including on-premises, private cloud setups, and Kubernetes clusters.
- **Helm Chart Support**: Create, manage, and deploy Helm charts for Kubernetes-based applications.
- **Version Control Integration**: Seamlessly create updates from your existing version control workflows.
- **Security-First Approach**: All packages and Helm charts are cryptographically signed to ensure integrity.
- **RESTful API**: Easily integrate Open Deploy into your existing toolchain.
- **Scalable Architecture**: Designed to handle deployments from small businesses to large enterprises.

## Getting Started

### Prerequisites

- Python 3.10+
- pip
- virtualenv (recommended)
- Helm 3.0+ (for Kubernetes deployments)
- kubectl (configured for your Kubernetes cluster)


## Usage

### Creating and Managing Helm Charts

Open Deploy provides tools to create, version, and manage Helm charts for your Kubernetes applications.

1. Create a new Helm chart:
   ```
   python scripts/create_helm_chart.py --name myapp --version 1.0.0
   ```

2. Package a Helm chart:
   ```
   python scripts/package_helm_chart.py --chart-path ./charts/myapp
   ```

3. Upload a Helm chart to Open Deploy's repository:
   ```
   python scripts/upload_helm_chart.py --chart-package myapp-1.0.0.tgz
   ```

### Deploying with Helm Charts

Use the `/deploy_helm_chart` API endpoint or the `deploy_helm_chart.py` script:

```
python scripts/deploy_helm_chart.py --chart myapp --version 1.0.0 --namespace mynamespace
```

This will deploy the specified Helm chart to your Kubernetes cluster.

## Helm Chart Repository

Open Deploy includes a Helm chart repository feature. You can add Open Deploy's Helm repository to your Kubernetes cluster with:

```
helm repo add open-deploy https://helm.opendeploy.example.com
helm repo update
```

Then, you can install charts from Open Deploy's repository:

```
helm install myapp open-deploy/myapp
```

## API Documentation

[Link to detailed API documentation]

## Contributing

We welcome contributions to Open Deploy! Please see our [Contributing Guide](CONTRIBUTING.md) for more details on how to get started.

## Support

For bug reports and feature requests, please use the [GitHub Issues](https://github.com/slashml/open-deploy/issues) page.

For general questions and discussions, join our [Community Forum](https://community.opendeploy.org).

## Acknowledgments

- This project was inspired by the need for an open-source alternative to proprietary enterprise software delivery platforms.
- Special thanks to all our contributors and the open-source community.
- We're grateful to the Helm project for their excellent work on Kubernetes package management.