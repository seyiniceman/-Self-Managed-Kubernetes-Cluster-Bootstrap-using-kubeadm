# Self-Managed Kubernetes Cluster Bootstrap using kubeadm

Provision a self-managed Kubernetes cluster using Terraform and bootstrap the cluster using kubeadm. Configure networking with Calico to create a production-style Kubernetes environment for learning and DevOps automation.

## Project Overview

This project demonstrates how to provision virtual machines using Terraform and bootstrap a fully functional Kubernetes cluster using kubeadm.

Unlike managed Kubernetes services such as Amazon EKS, this project focuses on building Kubernetes from the ground up. It includes configuring the control plane, joining worker nodes, installing the Calico Container Network Interface (CNI), and verifying cluster health.

The project demonstrates Infrastructure as Code (IaC), Linux administration, Kubernetes installation, cluster networking, and automation practices commonly used by DevOps engineers.

## Architecture Diagram

```text
                +----------------------+
                |      Developer       |
                +----------+-----------+
                           |
                           | terraform apply
                           v
               +-------------------------+
               |   Terraform Provision   |
               +-----------+-------------+
                           |
         +-----------------+------------------+
         |                                    |
         v                                    v
+----------------------+            +----------------------+
| Kubernetes Master    |            | Kubernetes Worker    |
| kubeadm init         |            | kubeadm join         |
+----------+-----------+            +----------+-----------+
           |                                   |
           +---------------+-------------------+
                           |
                           v
                  Install Calico CNI
                           |
                           v
                 Kubernetes Networking
                           |
                           v
                  kubectl get nodes
                           |
                           v
                 Cluster Ready
```

## Objectives

- Provision infrastructure using Terraform.
- Bootstrap a Kubernetes cluster using kubeadm.
- Configure Kubernetes networking using Calico.
- Join worker nodes to the control plane.
- Demonstrate Infrastructure as Code principles.
- Build a reusable Kubernetes deployment process.

## Technologies Used

- Terraform
- Kubernetes
- kubeadm
- Calico
- Linux
- Git
- Bash
- kubectl

## Repository Structure

- main.tf
- node.tf
- variables.tf
- install_k8s.sh
- calico.yaml
- remote-state/
- README.md

## Workflow

1. Provision infrastructure using Terraform.
2. Configure Linux dependencies.
3. Install Docker or container runtime.
4. Install kubeadm, kubelet and kubectl.
5. Initialize the control plane using `kubeadm init`.
6. Install the Calico networking plugin.
7. Join worker nodes using the generated join token.
8. Verify cluster status using `kubectl get nodes`.

## Prerequisites

- Terraform installed
- Linux virtual machines or cloud instances
- SSH access
- Internet connectivity
- kubectl
- kubeadm
- Container runtime

## Deployment Steps

1. Clone the repository.
2. Run `terraform init`.
3. Run `terraform plan`.
4. Run `terraform apply`.
5. Execute `install_k8s.sh`.
6. Run `kubeadm init` on the control plane.
7. Apply Calico:
   ```bash
   kubectl apply -f calico.yaml
   ```
8. Join worker nodes using the kubeadm join command.
9. Verify the cluster:
   ```bash
   kubectl get nodes
   ```

## Skills Demonstrated

- Kubernetes Cluster Administration
- kubeadm
- Cluster Bootstrap
- Infrastructure as Code (Terraform)
- Linux Administration
- Container Networking
- Kubernetes Networking (Calico)
- Bash Scripting
- Git
- Troubleshooting

## Project Outcome

Successfully provisioned infrastructure and deployed a self-managed Kubernetes cluster using kubeadm. Configured cluster networking with Calico, joined worker nodes to the control plane, and verified cluster health. This project demonstrates practical Kubernetes administration skills, Infrastructure as Code, and automation techniques commonly used in production DevOps environments.


# Author

**Seyi Akinmusere**

DevOps | Cloud Engineer | AWS | Terraform | Jenkins | Docker | Kubernetes

