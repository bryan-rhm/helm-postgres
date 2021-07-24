# helm-postgres

This is a simple helm chart for postgres, this charts launches:

- configmap
- statefulset
- service

## Requirements
- (helm v3)[https://helm.sh/docs/intro/install/]
- (helm diff)[https://github.com/databus23/helm-diff]
- (Helmfile)[https://github.com/roboll/helmfile]


## How to deploy 

From the root directory execute the following:
```bash
helmfile -e staging -f helm/postgres/helmfile.yaml apply
```

The vars folder could include values for multiple environments that overrides the original values.yaml file.


## Secrets

This charts deploys the postgres application with a sample password, for production applications I would recommend to use secrets instead and you could use sops to encrypt and decrypt files in the case that you want to keep the secrets encrypted in the repository, also helm has a sops plugin which makes the integrations pretty easy.

(SOPS)[https://github.com/mozilla/sops]
