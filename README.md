# Fluxer Helm Chart

[![Release Charts](https://github.com/Typositoire/fluxer-chart/actions/workflows/release.yml/badge.svg)](https://github.com/Typositoire/fluxer-chart/actions/workflows/release.yml)
[![Artifact Hub](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/fluxer)](https://artifacthub.io/packages/search?repo=fluxer)

A Helm chart for deploying Fluxer in Kubernetes.

## 📦 Helm Repository

This repository is published as a Helm chart repository using GitHub Pages.

**Repository URL**: `https://typositoire.github.io/fluxer-chart/`

## 🚀 Quick Start

### Add the Helm Repository

```bash
helm repo add fluxer-chart https://typositoire.github.io/fluxer-chart/
helm repo update
```

### Install the Chart

```bash
helm install my-fluxer fluxer-chart/fluxer-chart
```

### Install with Custom Values

```bash
helm install my-fluxer fluxer-chart/fluxer-chart -f custom-values.yaml
```

## 🔧 Configuration

To see all available configuration options:

```bash
helm show values fluxer-chart/fluxer-chart
```

### Key Configuration Options

| Parameter | Description | Default |
|-----------|-------------|---------|
| `replicaCount` | Number of replicas | `1` |
| `image.repository` | Image repository | `nginx` |
| `image.tag` | Image tag | `""` (uses appVersion) |
| `image.pullPolicy` | Image pull policy | `IfNotPresent` |
| `service.type` | Kubernetes service type | `ClusterIP` |
| `service.port` | Service port | `80` |
| `ingress.enabled` | Enable ingress | `false` |
| `autoscaling.enabled` | Enable autoscaling | `false` |

## 📚 Documentation

For more detailed documentation and examples, visit the [GitHub Pages site](https://typositoire.github.io/fluxer-chart/).

## 🛠️ Development

### Prerequisites

- [Helm 3](https://helm.sh/docs/intro/install/)
- [Kubernetes cluster](https://kubernetes.io/docs/setup/) (for testing)

### Local Testing

1. Install the chart locally:
   ```bash
   helm install test-release .
   ```

2. Verify the installation:
   ```bash
   helm list
   kubectl get all
   ```

3. Uninstall when done:
   ```bash
   helm uninstall test-release
   ```

### Packaging

To package the chart manually:

```bash
helm package .
```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is open source and available under the standard Helm chart license.

## 👤 Author

**Typositoire**
- GitHub: [@Typositoire](https://github.com/Typositoire)
- Email: davidyann88@gmail.com

## 🔗 Links

- [Helm Documentation](https://helm.sh/docs/)
- [Kubernetes Documentation](https://kubernetes.io/docs/)
- [ArtifactHub](https://artifacthub.io/)
