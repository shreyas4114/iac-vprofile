# iac-vprofile

## 📎 Related Repositories

➡️ [vprofile-action](https://github.com/user/vprofile-action): Microservices application deployed to this EKS cluster.

Infrastructure as Code (IaC) for deploying a production-ready AWS EKS (Elastic Kubernetes Service) cluster using Terraform and GitHub Actions.

## 🚀 Overview

This repository automates the creation and configuration of the Kubernetes infrastructure required to host the `vProfile` microservices application. It provisions:

- EKS Cluster
- VPC and Networking components
- IAM roles and policies
- Kubernetes provider setup
- Ingress Controller installation

---

## ⚙️ Tech Stack

- **Terraform** for Infrastructure as Code
- **AWS** (EKS, IAM, VPC)
- **GitHub Actions** for CI/CD
- **kubectl** for Kubernetes interaction
- **NGINX Ingress Controller**

---

## 🔄 GitHub Actions Workflow

The GitHub Actions workflow (`.github/workflows/vprofile-iac.yml`) automatically:

1. Initializes Terraform with remote S3 backend
2. Formats and validates code
3. Generates and applies a Terraform plan (on `main` branch push)
4. Updates the `kubeconfig` with the new EKS cluster
5. Installs NGINX Ingress Controller on the cluster

Trigger Paths:
- Push or PR to `main` or `stage` branch under `terraform/`

---

## 🛠️ Prerequisites

- AWS account with appropriate IAM permissions
- An S3 bucket for remote Terraform state
- GitHub repository secrets:
  - `AWS_ACCESS_KEY_ID`
  - `AWS_SECRET_ACCESS_KEY`
  - `BUCKET_TF_STATE`

---

## 📦 Outputs

After successful execution:
- EKS cluster endpoint and kubeconfig are configured
- Ingress controller is running and ready to accept microservices

---
