# kubectl-aws-ssm

This is a kubectl plugin that allows users to connect to eks nodes using `kubectl aws ssm` command which will initiate a session manager session to the ec2 instance.

## Prerequisites

- kubectl
- aws cli version 2
- session manager plugin

## Installation

To install the plugin, move the `kubectl-aws-ssm` executable file to anywhere on your PATH.

## Usage

You can use the plugin to connect to a node by its name or by a label selector.

To connect to a node by its name, run:

```bash
kubectl aws ssm node-name
```

To connect to a node by a label selector, run:

```bash
kubectl aws ssm -l selector
```

For example, to connect to a node with the label role=worker, run:

```bash
kubectl aws ssm -l role=worker
```

The plugin will find the node IP address and instance ID, and then use aws ssm start-session to initiate a session manager session to the EC2 instance.