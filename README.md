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

## Notes on deploying open source helms via GitHub

1. Create a `gh-pages` branch. This will auto run a workflow and you will be able to publish your helm charts here.
2. Add a `chart-release.yaml` file under `.github/workflows` similar to this repository.
3. Make sure you have set `fetch-depth: 0` on checkout action. Also avoid using `ref` set as it will probably break your deployment.
4. If you copy this `chart-release.yaml` file you will have to create a new release tagged as `x.x.x` (your semantic version) in order for your release to be published to `gh-pages`.
5. The `index.yaml` file required to use the chart will be automatically generated if you have reached this far.
6. You will be able to view your release under `https://<username>.github.io/<repository_name>` eg. https://tsigouris007.github.io/Falcon-CrowdStrike-Connector-Helm/
