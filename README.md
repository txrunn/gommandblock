# gommandblock

## Overview

`gommandblock` is a revolutionary platform designed to automate and simplify the deployment and management of Minecraft servers. It integrates seamlessly with Discord, allowing users to control their servers through chat commands. Utilizing K3s for lightweight Kubernetes clusters, Karpenter for efficient node provisioning, and ARM instances for cost-effective computing, `gommandblock` sets a new standard for gaming server infrastructure. Additionally, the integration of the Shulker Kubernetes operator enables advanced Minecraft server management capabilities directly within the Kubernetes ecosystem.

## Features

- **Discord Integration**: Manage Minecraft servers directly through Discord commands.
- **Dynamic Resource Allocation**: Utilizes Karpenter for smart, demand-based provisioning of Kubernetes nodes.
- **Cost Efficiency**: Leverages ARM instances to minimize infrastructure costs without sacrificing performance.
- **User Node Integration**: Allows users to add their PCs as compute nodes to the cluster, enhancing resource availability.
- **Shulker Operator Integration**: Harnesses the Shulker Kubernetes operator for specialized Minecraft server management within the Kubernetes environment.
- **Multi-Cloud and On-Premise Support**: Designed to run on any cloud provider that supports Kubernetes, as well as on-premise setups, offering unparalleled flexibility.

## Getting Started

### Prerequisites

- A Discord account and a created Discord bot for server management commands.
- Access to a Kubernetes cluster, with K3s installed for edge or on-premise environments.
- Karpenter set up in your Kubernetes cluster for dynamic node provisioning.

### Installation

1. **Set Up the Discord Bot**:
   - Clone the repository and navigate to the bot directory.
   - Configure your bot token and preferences in `config.py`.
   - Run the bot using Python.

2. **Deploy `gommandblock` to Kubernetes**:
   - Apply the Kubernetes manifests found in `/k8s`, adjusting for your specific environment and credentials.
   - Ensure Shulker and Karpenter are properly configured within your cluster.

3. **Add Your PC as a Compute Node (Optional)**:
   - Follow the instructions in `COMPUTE_NODE_SETUP.md` to register your PC as a node in the cluster using K3s.

## Architecture

`gommandblock` leverages a microservices architecture, encapsulated within Kubernetes, to provide a scalable and resilient platform for Minecraft server management. This section would benefit from Mermaid diagrams to visualize the architecture.

### Components

- **Discord Bot**: Interfaces with the Discord API to receive commands and manage servers.
- **Secure API / mcd**: A Go-based API that handles authentication, server management commands, and interacts with the Kubernetes API.
- **Kubernetes Cluster**: Hosts the Minecraft servers and `gommandblock` components, dynamically scaled by Karpenter.
- **Shulker Operator**: Manages the lifecycle of Minecraft server instances within the Kubernetes cluster.

## Repository Structure

```plaintext
/gommandblock
├── /docs                # Documentation
├── /src
│   ├── /bot             # Discord bot source code
│   └── /api             # Secure API source code
├── /k8s                 # Kubernetes manifests and Shulker configuration
├── /terraform           # Terraform scripts for infrastructure provisioning
└── /blocks              # Minecraft server configurations and modpacks
```

## Contributing

We welcome contributions from the community. Whether you're looking to fix a bug, add a feature, or improve documentation, please see `CONTRIBUTING.md` for guidelines on how to get started.

## License

`gommandblock` is open-sourced under the MIT License. See `LICENSE` for more details.

