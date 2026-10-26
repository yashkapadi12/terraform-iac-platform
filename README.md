# Terraform IaC Platform

Reusable **Terraform modules** with remote-state layout and a sample VPC stack (AWS).

## Structure

```
terraform/
  modules/network/   # VPC, subnets, routing
  environments/dev/  # Example environment wiring
```

## Prerequisites

- Terraform >= 1.5
- AWS credentials (for `plan`/`apply` — optional for fmt/validate)

## Commands

```bash
cd terraform/environments/dev
terraform init
terraform fmt -recursive
terraform validate
# terraform plan   # requires AWS creds
```

## Design notes

- Modules expose clear inputs/outputs for composition
- Environment folder pins provider versions and backend config
- Intended pattern: PR → `terraform plan` in CI → approved apply
