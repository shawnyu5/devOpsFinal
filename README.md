# DevOps final project

## Argo CD deployment

Argo CD was installed though a helm chart.

Create a `argocd` namespace in the cluster: `kubectl create namepace argocd`

Add Argo helm repo and install argo in the namepace

`helm repo add argo https://argoproj.github.io/Argo-helm`

`helm install my-argo-cd argo/argo-cd --version 5.28.1 -n argocd`

Port forward web address from pod

`kubectl port-forward service/my-argo-cd-argocd-server -n argot 8080:443`

Get the default admin password

`kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d`
