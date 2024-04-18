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
curl -sk https://raw.githubusercontent.com/gmeghnag/openshift-gitops-install/main/argo/Application.yaml | oc create -f -
```
