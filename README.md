Перед запуском helm-релизов и istio-компонентов:
```
minikube start --memory=16384 --cpus=4
```

```
minikube addons enable istio-provisioner & minikube addons enable istio
```

```
kubectl label namespace default istio-injection=enabled
```

```
sudo minikube tunnel
```

Prometheus:
```
kubectl apply -f istio/prometheus.yaml 
```

Kiali:
```
kubectl apply -f istio/kiali.yaml & kubectl port-forward svc/kiali -n istio-system 20001:20001
```

Jaeger:
```
kubectl apply -f istio/jaeger.yaml 
```
