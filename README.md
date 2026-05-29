# ☁️ ScottsTechX Terraform

<p align="center">
  <img src="https://img.shields.io/badge/Infrastructure-as-Code-00ff88?style=for-the-badge&logo=terraform&logoColor=black" alt="Terraform"/>
  <img src="https://img.shields.io/badge/Open-Source-00ff88?style=for-the-badge&logo=github&logoColor=black" alt="Open Source"/>
  <img src="https://img.shields.io/badge/DevOps-Automation-00ff88?style=for-the-badge&logo=terminal&logoColor=black" alt="DevOps"/>
</p>

> **Define, provision, and manage cloud infrastructure as code.**

---

## ⚡ What It Does

Terraform automates cloud infrastructure provisioning across AWS, GCP, Azure, and 100+ providers — spin up vulnerable cloud environments for security research, CTF challenges, or red team engagements.

## 🚀 Quick Start

```bash
# Initialize Terraform
terraform init

# Format configuration
terraform fmt

# Validate configuration
terraform validate

# Plan changes
terraform plan

# Apply changes
terraform apply

# Destroy resources
terraform destroy
```

## 🏗️ Common Patterns

```hcl
# AWS Security Research VPC
resource "aws_vpc" "research" {
  cidr_block           = "10.0.0.0/16"
  enable_dns_hostnames = true
  enable_dns_support   = true
}

resource "aws_subnet" "public" {
  vpc_id                  = aws_vpc.research.id
  cidr_block              = "10.0.1.0/24"
  map_public_ip_on_launch = true
}

resource "aws_security_group" " pentest" {
  vpc_id = aws_vpc.research.id
  ingress {
    from_port   = 22
    to_port     = 22
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
}
```

## ☁️ Supported Providers

| Provider | Use Case |
|----------|---------|
| AWS | Cloud infrastructure, security research labs |
| GCP | Google Cloud security testing |
| Azure | Microsoft cloud environments |
| DigitalOcean | Droplets for CTF/sandbox environments |

## 🛡️ Security Research Applications

- **CTF cloud challenges** — provision vulnerable infrastructure
- **Red team environments** — replicate target cloud architecture
- **Vulnerability testing** — isolated cloud sandboxes
- **Bug bounty** — test cloud misconfigurations

---

## 📜 License

MIT License — [ScottsTechX](https://github.com/fredscottsbulls) © 2026
