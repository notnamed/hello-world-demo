0) Clone the repository:

`git clone https://github.com/notnamed/hello-world-demo.git`

1) Create the demo namespace:

`kubectl create ns tectonic-demo`

2) Create deployment:

```
cd hello-world-demo/k8s
kubectl create -f hello-world-deployment.yaml
```

3) Create service:

`kubectl create -f hello-world-service.yaml`

4) Create a new Prometheus in the tectonic-demo namespace

`kubectl create -f prometheus-helloworld.yaml`

5) Create Service Monitor:

`kubectl create -f prometheus-servicemonitor.yaml`

6) Create ServiceAccount:

`kubectl create -f prometheus-serviceaccount.yaml`

7) Create Roles:

`kubectl create -f prometheus-roles.yaml`

8) Create Role Bindings:

`kubectl create -f prometheus-rolebindings.yaml`

8) Create ConfigMap:

`kubectl create -f prometheus-configmap.yaml`

9) Create service for prometheus

`kubectl create -f prometheus-service.yaml`

10) Add alerts to AlertManager:

`kubectl -n tectonic-system create secret generic alertmanager-main --from-literal=alertmanager.yaml="$(< alertmanager.yaml)" --dry-run -oyaml | kubectl -n tectonic-system replace secret --filename=-`


Optionally if you are deploying on bare metal or VMware and want to setup ingress for Hello-world and Prometheus instance of hello-world refer to the following two YAML files hello-world-ingress.yaml and prometheus-ingress.yaml for examples.
