

Creating a sealed secret
========================

$ kubectl create secret docker-registry github-container-registry-credentials \
  --namespace flux-big-mens-dev \
  --docker-server=ghcr.io \
  --docker-username=lukeanderson93 \
  --docker-password= \
  --dry-run=client \
  -o yaml | kubeseal --format=yaml --cert=pub-sealed-secrets.pem > apps/big-mens/github-container-registry-credentials-sealed.yaml
