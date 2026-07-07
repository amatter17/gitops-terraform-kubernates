# Monitoring

This directory contains the monitoring components for the DEPI GitOps Kubernetes project.

## Overview

The monitoring stack is built using the Prometheus Operator (`kube-prometheus-stack`) and provides:

- Prometheus for metrics collection
- Grafana for visualization
- Alertmanager for alert routing
- Node Exporter for node metrics
- kube-state-metrics for Kubernetes object metrics

## Directory Structure

```
monitoring/
├── alerts/        # Prometheus alert rules
├── dashboards/    # Grafana dashboards
├── docs/          # Monitoring documentation
├── helm/          # Helm configuration files
└── manifests/     # Kubernetes manifests
```

## Deployment

Create the monitoring namespace:

```bash
kubectl apply -f manifests/namespace.yaml
```

Deploy the monitoring stack:

```bash
helm install depi-monitoring prometheus-community/kube-prometheus-stack \
  -n monitoring \
  -f helm/custom-values.yaml
```

## Components

- Prometheus
- Grafana
- Alertmanager
- Node Exporter
- kube-state-metrics

## Status

Current implementation includes:

- Monitoring namespace
- Helm configuration
- Grafana dashboards
- Prometheus alert rules

Future work:

- Alertmanager notifications
- Application monitoring
- Custom dashboards
