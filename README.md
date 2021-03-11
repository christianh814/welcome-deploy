# Welcome App Deployment
Deployment manifests for the [Welcome-App application](https://github.com/christianh814/welcome-app).

# Install ArgoCD

Install the Operator

```shell
oc apply -k https://github.com/RedHatWorkshops/argocd-getting-started/resources/manifests/argocd-operator-install
```

Install an instance

```shell
until oc apply -k https://github.com/RedHatWorkshops/argocd-getting-started/resources/manifests/argocd-instance do ; sleep 3 ; done
```

# Install Sealed Secrets

Install it using Kustomzie. This installs it in the `sealed-secrets` namespace.

```shell
oc apply -k https://github.com/christianh814/openshift-cluster-config/manifests/sealed-secrets/base/
```

# Install Tekton

Install OpenShift Pipelines

```shell
oc apply -k https://github.com/christianh814/openshift-cluster-config/manifests/pipelines/base/
```

# Install this Repo

To install this repo, run the following

```shell
oc apply -k https://github.com/christianh814/welcome-deploy/cicd/argocd
```
