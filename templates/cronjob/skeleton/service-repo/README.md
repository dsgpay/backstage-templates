# ${{ values.serviceName }}

${{ values.description }}

## CI/CD

Push to `main` → builds Docker image → pushes to ECR → updates image tag directly in [prod-gitops](https://github.com/dsgpay/prod-gitops).

## Setup

Before CI works, add these secrets to this repo (or as org-level secrets):
- `AWS_ROLE_ARN` — IAM role ARN for OIDC authentication with ECR
- `GITOPS_TOKEN` — GitHub token with `repo` scope on `dsgpay/prod-gitops` for updating deployments

## Resources

- [Backstage catalog](https://backstage.dsgpay.com/catalog/default/component/${{ values.serviceName }})
- [ArgoCD](https://prod-argocd.dsgpay.com/applications/${{ values.serviceName }})
