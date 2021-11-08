# Local KinD Kubernetes Setup w/ ArgoCD

This sets up a local Kubernetes cluster using KinD (Kubernetes in Docker) and installs ArgoCD and uses it to sync the following applications onto the cluster:

- argocd (argocd syncs itself!)
- nginx-ingress
- cert-manager
- sealed-secrets
- linkerd

## Getting Started

- Make sure you have KinD installed:

    ```sh
    brew install kind
    ```

- Create the KinD cluster from the config:

    ```sh
    kind create cluster --config ./kind/v1.20-config.yaml
    ```

- Install ArgoCD using `kustomize` so it can fetch all the other applications

    ```sh
    kubectl apply -k ./argocd
    ```
