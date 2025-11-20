# devops-eks-terraform-github-actions
project deployment through terraform

devops-eks-terraform-github-actions/
├── microservices/
│   └── app1/
│       ├── app.py
│       ├── requirements.txt
│       └── Dockerfile
├── terraform/
│   ├── providers.tf
│   ├── variables.tf
│   ├── main.tf
│   ├── vpc.tf
│   ├── eks.tf
│   ├── iam.tf
│   └── outputs.tf
├── k8s-manifests/
│   ├── namespace.yaml
│   ├── deployment.yaml
│   └── service.yaml
├── .github/
│   └── workflows/
│       └── cicd.yaml
└── README.md








# DevOps Project: Terraform + EKS + GitHub Actions CI/CD

This project demonstrates a complete DevOps workflow:

- Infrastructure as Code with **Terraform**
- **AWS EKS** cluster for running containers
- **Dockerized Flask microservice**
- **GitHub Actions CI/CD pipeline**
- Automatic deployment to **EKS** on every push to `main`

## Tech Stack

- AWS (EKS, VPC, IAM, ECR)
- Terraform
- Docker
- Kubernetes
- GitHub Actions
- Python + Flask

## How It Works

1. Terraform provisions:
   - VPC, subnets, NAT
   - EKS cluster + node group
2. Application is built from `microservices/app1` as a Docker image.
3. GitHub Actions:
   - Builds & pushes the image to Amazon ECR.
   - Updates Kubernetes deployment manifests.
   - Applies manifests to EKS cluster.

## Steps to Use

1. Create an **ECR repository** in your AWS account.
2. Update:
   - `k8s-manifests/deployment.yaml` image placeholder (first time).
3. Set GitHub Secrets:
   - `AWS_ACCESS_KEY_ID`
   - `AWS_SECRET_ACCESS_KEY`
   - `AWS_REGION`
   - `ECR_REPOSITORY`
   - `EKS_CLUSTER_NAME`
4. Run Terraform:
   ```bash
   cd terraform
   terraform init
   terraform apply
