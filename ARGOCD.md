#

ArgoCD commands

$ kubectl create namespace argocd
$ kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

$ kubectl get svc -n argocd

Access argo app without creating a service
$ kubectl port-forward svc/argocd-server -n argocd 8080:443

$ kubectl get secret argocd-initial-admin-secret -n argocd -o yaml
$ echo b2tLbnZTdFdJalcwa0pNbw== | base64 --decode
okKnvStWIjW0kJMo% # ignore %

or
$ kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 --decode && echo
