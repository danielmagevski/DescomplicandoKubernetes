# Descomplicando o Kubernetes - Expert Mode

## DAY-14

### O que iremos ver hoje?

Hoje é um dia particularmente fascinante! Vamos desbravar os territórios do Kubernetes, explorando a magia do Horizontal Pod Autoscaler (HPA), uma ferramenta indispensável para quem almeja uma operação eficiente e resiliente. Portanto, afivelem os cintos e preparem-se para uma jornada de descobertas. 


## Comandos utilizados

<p>minikube addons enable metrics-server</p>
<p>kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml</p>
<p>helm repo add metrics-server https://kubernetes-sigs.github.io/metrics-server/</p>
<p>helm repo update</p>
<p>helm upgrade --install --set args={--kubelet-insecure-tls} metrics-server metrics-server/metrics-server --namespace kube-system</p>
<p>kubectl get pods -n kube-system | grep metrics-server</p>
<p>kubectl top nodes</p>
<p>kubectl top pods</p>
<p>kubectl apply -f nginx-deployment-hpa.yaml</p>
<p>kubectl apply -f nginx-deployment.yaml</p>
<p>kubectl get deployment</p>
<p>kubectl get pods</p>

