# 🏗️ Cluster Architecture Overview

> 🔗 [Back to Main README](./README.md)


This document outlines the basic server architecture for the Kubernetes cluster environment. Each server is designated with its respective hostname and IP address.

## 🖥️ Server Table

| Hostname      | IP Address   | Role Description               |
|---------------|--------------|-------------------------------|
| `kubectl`     | 10.0.3.10     | Cluster management node (CLI) |
| `kubectl-sbx` | 10.0.3.14     | Cluster management node (CLI) - Sandbox |
| `kubenode1`   | 10.0.3.11     | Worker node #1                |
| `kubenode2`   | 10.0.3.12     | Worker node #2                |
| `pod-registry`| 10.0.3.13     | Internal container image registry |

## 🧭 Notes

- `kubectl` acts as the control interface for deploying and managing cluster resources.
- `kubenode1` and `kubenode2` are responsible for running application pods and handling workloads.
- `pod-registry` provides a local image store for faster, secure access within the cluster.