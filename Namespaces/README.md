# Imperative Commands Guide

This guide focuses on the use of imperative commands in Kubernetes, which are useful for executing one-time tasks and generating template definitions quickly. Such commands are particularly helpful during exams to save time.

## Preliminaries

Before using the commands, familiarize yourself with two important options:

- `--dry-run`: Runs the command without creating resources. Use `--dry-run=client` to test if a resource can be created without actually creating it.
- `-o yaml`: Outputs the resource definition in YAML format to the screen.

These options can be combined with Linux output redirection to quickly generate a resource definition file, which can then be modified and used to create resources.

### Example Command

```bash
kubectl run nginx --image=nginx --dry-run=client -o yaml > nginx-pod.yaml

```bash
kubectl run nginx --image=nginx

### Generate POD Manifest YAML file (-o yaml). Don't create it(--dry-run)
```bash
kubectl run nginx --image=nginx --dry-run=client -o yaml
