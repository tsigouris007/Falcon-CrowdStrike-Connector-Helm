# Falcon-CrowdStrike-Connector-Helm
Helm chart for Falcon CrowdStrike Connector. \
This is a minimal first approach. You can modify / define things accordingly.

## Prerequisites

- Helm: https://helm.sh/docs/intro/install/
- Any k8s. I used minikube to test this: https://minikube.sigs.k8s.io/docs/start/

## Install / Uninstall

To install this chart simply run in the root folder of this repository:
```bash
~$ helm install falcon falcon-crowdstrike/
```

To uninstall this chart run:
```bash
~$ helm uninstall falcon
```

## Secrets

Under the `values.yaml` file you will find a block of secret values as shown:
```yaml
secrets:
  CLIENT_ID: ""
  CLIENT_SECRET: ""
  API_BASE_URL: ""
```

Fill them accordingly.

## TODO

Move secrets to native k8s `Secret` object.
