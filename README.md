# openshift-gitops-install
```
oc apply -k https://github.com/gmeghnag/openshift-gitops-install
```
```
cat << EOF | oc create -f -
apiVersion: argoproj.io/v1beta1
kind: ArgoCD
metadata:
  name: example
  namespace: openshift-gitops
spec:
  server:
    route:
      enabled: true
EOF
```
```
curl -sk https://raw.githubusercontent.com/redhat-developer/openshift-gitops-getting-started/main/argo/app.yaml | oc create -f -
oc label namespace spring-petclinic argocd.argoproj.io/managed-by=openshift-gitops
```
