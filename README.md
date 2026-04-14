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

