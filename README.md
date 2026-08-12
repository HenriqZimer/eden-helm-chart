# Eden Helm Chart Repository

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Helm Version](https://img.shields.io/badge/Helm-v3-blue)](https://helm.sh)
[![Artifact Hub](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/eden-helm-chart)](https://artifacthub.io/packages/search?repo=eden-helm-chart)

This repository contains a production-ready Helm chart for deploying [Eden](https://docs.linuxserver.io/images/docker-eden/) on Kubernetes.

## About Eden

Eden is a free and open-source Nintendo Switch emulator. This chart deploys the
[linuxserver.io](https://docs.linuxserver.io/images/docker-eden/) build, which serves the full
emulator desktop in your browser over KasmVNC — no local install needed, play from any device on
your network:

- 🎮 Full Switch emulator desktop, streamed over the browser (KasmVNC)
- 🖥️ No client install — works from any modern browser
- 🗄️ Config persistence via a mounted `/config` volume
- 🎯 Bring your own ROMs library via `extraVolumes`
- ⚡ Optional VA-API GPU passthrough for hardware-accelerated rendering
- 🔌 Optional integration with [RomM's Emulator Streaming](https://docs.romm.app/latest/using/emulator-streaming/)

## Quick Start

### Add Helm Repository

```bash
helm repo add eden https://henriqzimer.github.io/eden-helm-chart/
helm repo update
```

### Install Chart

```bash
helm install eden eden/eden
```

For detailed installation instructions and configuration options, see the [chart README](chart/README.md).

## Repository Structure

```
.
├── chart/              # Helm chart for Eden
│   ├── Chart.yaml      # Chart metadata
│   ├── values.yaml     # Default configuration values
│   ├── README.md       # Detailed chart documentation
│   └── templates/      # Kubernetes manifest templates
├── LICENSE             # Repository license
└── README.md           # This file
```

## Documentation

- **[Chart Documentation](chart/README.md)** - Complete installation and configuration guide
- **[linuxserver.io Eden Docs](https://docs.linuxserver.io/images/docker-eden/)** - Upstream image documentation
- **[Values Reference](chart/values.yaml)** - All available configuration options

## Prerequisites

- Kubernetes 1.19+
- Helm 3.0+
- Persistent storage, if you enable `persistence.config` (NFS, local-path, or cloud storage)
- (Optional) Ingress controller
- (Optional) cert-manager for automatic TLS
- (Optional) A node exposing `/dev/dri` for GPU passthrough

## Features

This Helm chart provides:

- ✅ Production-ready Kubernetes Deployment/Service
- ✅ Optional persistent `/config` volume (settings)
- ✅ `extraVolumes`/`extraVolumeMounts` for a ROMs library
- ✅ Optional Ingress with TLS support
- ✅ Resource limits and requests
- ✅ Readiness/liveness probes
- ✅ Configurable ServiceAccount
- ✅ Optional VA-API (`/dev/dri`) GPU passthrough
- ✅ Optional RomM Emulator Streaming broker port

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request. See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

This Helm chart is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

Eden itself is licensed under its own terms. See the [Eden project](https://eden-emu.dev/) and the
[linuxserver.io image](https://github.com/linuxserver/docker-eden) for more information.

## Support

- 🐛 [Report Issues](https://github.com/HenriqZimer/eden-helm-chart/issues)
- 💬 [Discussions](https://github.com/HenriqZimer/eden-helm-chart/discussions)
- 📖 [Documentation](chart/README.md)

---

Made with ❤️ for the retro gaming community
