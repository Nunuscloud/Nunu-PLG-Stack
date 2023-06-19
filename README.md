# PLG-Stack
- Loki: Save log data
- Promtail: Collect logs
- Grafana: Visualize the data
- Prometheus: Collects metric data and alerts
- Alertmanager: 

# Install
- Create Namespaces
```
kubectl create ns monitoring \
kubectl create ns loki
```
\n
- Helm Repo Add
```
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
```
```
helm repo add grafana https://grafana.github.io/helm-charts
```
```
helm repo update
```
- Kube-Prometheus-Stack (AlertManager, Prometheus, Grafana)
```
helm install kube-prometheus-stack prometheus-community/kube-prometheus-stack --version 45.7.1 \
-f ./Kube-Prometheus-Stack/values.yaml --namespace monitoring
```
- Loki
```
helm install loki grafana/loki --version 2.16.0 -f ./Loki/values.yaml --namespace loki
```
- Promtail
```
helm install promtail grafana/promtail --version 6.0.0 -f ./Promtail/values.yaml --namespace loki
```
