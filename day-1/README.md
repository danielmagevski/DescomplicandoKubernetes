# Descomplicando o Kubernetes - Expert Mode

## DAY-1

### O que iremos ver hoje?

Durante o Day-1 nós vamos entender o que é um container, vamos falar sobre a importância do container runtime e do container engine. Durante o Day-1 vamos entender o que é o Kubernetes e sua arquitetura, vamos falar sobre o control plane, workers, apiserver, scheduler, controller e muito mais!
Será aqui que iremos criar o nosso primeiro cluster Kubernetes e realizar o deploy de um pod do Nginx. 
O Day-1 é para que eu possa me sentir mais confortável com o Kubernetes e seus conceitos iniciais.

## Comandos utilizados

<p>kind get clusters</p>
<p>kubectl get nodes</p>
<p>kubectl get namespaces</p>
<p>kubectl get pod -n kube-system</p>
<p>kubectl get pods -A</p>
<p>kubectl get pods -A -o wide</p>
<p>kubectl run nginx --image nginx</p>
<p>kubectl delete pod nginx</p>
<p>kubectl run meu-nginx --image nginx --dry-run=client -o yaml > pod-template.yaml</p>
<p>kubectl expose pod meu-nginx</p>
<p>kubectl apply -f pod-template.yaml</p>
<p>kubectl get all</p>
<p>kubectl get pod,service</p>
<p>kubectl get pod,svc</p>
<p>kubectl delete -f pod-template.yaml</p>
<p>kubectl delete service nginx</p>
