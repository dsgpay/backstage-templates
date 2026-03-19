# ${{ values.serviceName }}

${{ values.description }}

## CI/CD

Push to `main` → builds Docker image → pushes to ECR → updates image tag directly in [prod-gitops](https://github.com/dsgpay/prod-gitops).

## Setup

Before CI works, configure these in GitHub Actions:

Org-level variables (Settings → Variables):
- `AWS_ACCOUNT_ID` — AWS account ID for ECR image registry
- `AWS_REGION` — AWS region for ECR (e.g. `ap-southeast-1`)

Secrets (org-level or repo-level):
- `GITOPS_PAT` — GitHub token with `repo` scope on `dsgpay/prod-gitops` for updating deployments

## Resources

- [Backstage catalog](https://backstage.dsgpay.com/catalog/default/component/${{ values.serviceName }})
- [ArgoCD](https://prod-argocd.dsgpay.com/applications/${{ values.serviceName }})
