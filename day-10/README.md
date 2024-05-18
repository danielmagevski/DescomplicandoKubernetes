# Descomplicando o Kubernetes - Expert Mode

## DAY-10

### O que iremos ver hoje?

Agora que você já sabe o que é o ingress e como ele funciona, vamos adicionar o Cert-Manager com o Let's Encrypt ao cluster e criar um certificado SSL para o nosso domínio. Além disso, vamos aprender o que são e como funcionam as Annotations e Labels no Kubernetes.

## Comandos utilizados

<p>kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.14.1/cert-manager.yaml</p>
<p>kubectl get pods -n cert-manager</p>
<p>kubectl apply -f issuer-staging.yaml</p>
<p>kubectl apply -f cluster-issuer-prod.yaml</p>
<p>kubectl apply -f ingress.yaml</p>
<p>kubectl get certificates</p>
<p>kubectl get orders</p>
<p>kubectl get pods redis -o jsonpath='{.metadata.annotations}'</p>
<p>htpasswd -c auth daniel</p>
<p>kubectl create secret generic giropops-senhas-users --from-file=auth</p>
<p>kubectl apply -f ingress2.yaml</p>
<p>kubectl run nginx --image=nginx --port=80</p>
<p>kubectl expose deployment nginx --port=80</p>
<p>curl -v https://k8s.labdev.cloud</p>
<p>for i in {1..10}; do curl -s -o /dev/null -w "%{http_code}\n" https://k8s.labdev.cloud; done</p>




