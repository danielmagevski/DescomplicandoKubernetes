# Descomplicando o Kubernetes - Expert Mode

## DAY-12

### O que iremos ver hoje?

Hoje o nosso objetivo é continuar avançando na utilização do Prometheus juntamente com o nosso cluster Kubernetes.

Já vimos como fazer a instalação do kube-prometheus, peça super importante nesse momento. Porém precisamos começar a explorar além de sua instalação, precisamos começar a entender como ele funciona e como nós podemos interagir com ele.


## Comandos utilizados

<p>kubectl get servicemonitors -n monitoring</p>
<p>kubectl get servicemonitor prometheus-k8s -n monitoring -o yaml</p>
<p>kubectl apply -f nginx-deployment.yaml</p>
<p>kubectl get pods</p>
<p>kubectl get deployments</p>
<p>kubectl apply -f nginx-service.yaml</p>
<p>kubectl get services</p>
<p>kubectl apply -f nginx-service-monitor.yaml</p>
<p>kubectl get servicemonitors</p>
<p>kubectl port-forward -n monitoring svc/prometheus-k8s 39090:9090</p>
<p>curl http://localhost:39090/api/v1/targets</p>
<p>kubectl apply -f nginx-pod-monitor.yaml</p>
<p>kubectl get podmonitors</p>
<p>kubectl describe podmonitors nginx-podmonitor</p>
<p>kubectl describe servicemonitors nginx-servicemonitor</p>
<p>kubectl apply -f nginx-pod.yaml</p>
<p>kubectl apply -f nginx-prometheus-rule.yaml</p>
<p>kubectl apply -f servicemonitor.yaml</p>
<p>kubectl get prometheusrules -n monitoring nginx-prometheus-rule -o yaml</p>
<p>kubectl port-forward -n monitoring svc/alertmanager-main  39093:9093</p>
<p>kubectl get configmaps -n monitoring</p>
<p>kubectl get configmap prometheus-k8s-rulefiles-0 -n monitoring -o yaml</p>



