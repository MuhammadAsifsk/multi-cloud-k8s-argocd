# 🚀 AWS EKS Cluster with Terraform

This module provisions an **Amazon Elastic Kubernetes Service (EKS)** cluster using Terraform.  
It is part of the **Multi-Cloud Kubernetes with ArgoCD** project.

---

## 📂 Files Overview
- `provider.tf` → AWS provider configuration  
- `variables.tf` → Input variables (region, cluster name, instance type)  
- `main.tf` → EKS cluster definition (using terraform-aws-modules/eks)  
- `outputs.tf` → Cluster name and endpoint outputs  

---

## 🛠️ Prerequisites
- Terraform installed (`terraform -version`)  
- AWS CLI configured (`aws configure`)  
- kubectl installed (`kubectl version --client`)  
- An existing VPC + Subnets in AWS (replace IDs in `main.tf`)  

---

## ⚡ Deployment Steps

1. **Initialize Terraform**
   ```bash
   terraform init

Review the Plan

terraform plan


Apply the Configuration

terraform apply -auto-approve


Update kubeconfig to access the cluster

aws eks update-kubeconfig --region us-east-1 --name multi-cloud-eks


Verify cluster is running

kubectl get nodes

🧹 Cleanup

To destroy all resources created:

terraform destroy -auto-approve
