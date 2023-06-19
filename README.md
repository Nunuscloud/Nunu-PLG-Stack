# Loki-Stack
- Loki: Save log data
- Promtail: Collect logs
- Grafana: Visualize the data
- Prometheus: Collects metric data and alerts

# Install
```
kubectl create ns monitoring \
kubectl create ns loki
```
- Kube-Prometheus-Stack
```
helm install kube-prometheus-stack prometheus-community/kube-prometheus-stack --version 45.7.1 \
-f ./Kube-Prometheus-Stack/values.yaml --namespace monitoring

```
