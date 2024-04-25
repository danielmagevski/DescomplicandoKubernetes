# Descomplicando o Kubernetes - Expert Mode

## DAY-7

### O que iremos ver hoje?

Hoje é dia de falar sobre dois resources muito importantes para o Kubernetes, o **StatefulSet** e o **Service**. Vamos mostrar como criar e administrar **StatefulSets** para que você possa criar aplicações que precisam manter a identidade do **Pod** e persistir dados em volumes locais. Caos bem comuns de uso de StatefulSets são bancos de dados, sistemas de mensageria e sistemas de arquivos distribuídos.

Outra peça super importante que iremos falar hoje é sobre o Service. O Service é um objeto que permite que você expor uma aplicação para o mundo externo. Ele é responsável por fazer o balanceamento de carga entre os Pod que estão sendo expostos e também por fazer a resolução de nomes DNS para os Pods que estão sendo expostos. Temos diversos tipos de Services e iremos falar sobre eles hoje.

## Comandos utilizados

<p>kubectl apply -f nginx-statefulset.yaml</p>
<p>kubectl get statefulset</p>
<p>kubectl describe statefulset nginx</p>
<p>kubectl get pods</p>
<p>kubectl get statefulsets.apps -o yaml</p>
<p>kubectl apply -f nginx-headless-service.yaml</p>
<p>kubectl describe service nginx</p>
<p>kubectl delete svc nginx</p>
<p>kubectl delete statefulset nginx</p>
<p>kubectl delete -f statefulset-nginx.yaml</p>
<p>kubectl delete -f nginx-headless-service.yaml</p>
<p>kubectl delete pvc nginx-persistente-storage-nginx-0</p>
<p>kubectl get endpoints meu-service</p>
<p>kubectl expose deployment meu-deployment --port=80 --type=NodePort</p>
<p>kubectl create deployment nginx --image nginx --port 80</p>
<p>kubectl expose deployment nginx --type LoadBalancer</p>
<p>kubectl expose deployment meu-deployment --port=80 --target-port=8080</p>
<p>kubectl expose deployment meu-deployment --type=LoadBalancer --port=80 --target-port=8080</p>
<p>kubectl create service externalname meu-service --external-name meu-db.giropops.com.br</p>
<p>kubectl get endpoints meu-service</p>
<p>kubectl get endpoints -A</p>
<p>kubectl describe endpoints meu-service</p>
<p>kubectl delete service meu-service</p>
<p>kubectl delete -f meu-service.yaml</p>
