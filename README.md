# nginx Helm chart (local)

This repository contains a minimal Helm chart for deploying nginx under ./helm-charts/nginx-chart.

Commands:

- Install chart (local):
  helm install my-nginx ./helm-charts/nginx-chart -f ./helm-charts/nginx-chart/values.yaml

- Upgrade or install:
  helm upgrade --install my-nginx ./helm-charts/nginx-chart -f ./helm-charts/nginx-chart/values.yaml

- Uninstall:
  helm uninstall my-nginx

- Render templates locally:
  helm template my-nginx ./helm-charts/nginx-chart -f ./helm-charts/nginx-chart/values.yaml

- Lint chart:
  helm lint ./helm-charts/nginx-chart

Kubernetes quick checks:
  kubectl get pods
  kubectl get svc
  kubectl get ingress

Notes:
- Ingress is optional and controlled by values.ingress.enabled in values.yaml.
- Chart path: ./helm-charts/nginx-chart

Flux bootstrap examples:

- Bootstrap Flux on GitHub (creates repo or connects to existing; replace placeholders):
  flux bootstrap github \
    --owner=GITHUB_USER \
    --repository=REPO \
    --branch=main \
    --path=./flux \
    --personal

- Bootstrap Flux with an existing repo via HTTPS/SSH (use when you already have a repo):
  flux bootstrap git \
    --git@github.com:kaustubhsonar/demo.flux.git \
    --branch=main \
    --path=./flux

Notes:
- For private repos, ensure you have proper credentials (SSH key or GitHub token).
- flux bootstrap will create the flux-system namespace and install Flux controllers.
- After bootstrap, verify with:
  kubectl -n flux-system get pods
  flux check

