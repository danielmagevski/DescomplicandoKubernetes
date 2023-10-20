# Descomplicando o Kubernetes - Expert Mode

## DAY-6

### O que iremos ver hoje?

Durante o dia de hoje nós vamos aprender tudo sobre volumes, hoje é o dia de você finalmente descomplicar os volumes no Kubernetes!

Hoje nós iremos entender e configurar o que é um configmap, um persistente volume (PV) e um persistent volume claim (PVC)! E para isso iremos utilizar como exemplo diferentes tipos de clusters Kubernetes! Calma, eu explico melhor!

Para ajudar no nosso aprendizado sobre volumes, vamos utlizar diferentes clusters Kubernetes! Vamos ter exemplos utilizando EKS, kind e instâncias em cloud providers.

Então fique ciente de que hoje é o dia onde você irá descomplicar volumes no Kubernetes! #VAIIII.

## Comandos utilizados

<p>kubectl get storageclass</p>
<p>kubectl describe storageclass standard</p>
<p>kubectl apply -f storageclass.yaml</p>
<p>kubectl describe storageclass giropops</p>
<p>kubectl get pv -A</p>
<p>kubectl apply -f pv.yaml</p>
<p>kubectl get pv</p>
<p>kubectl describe pv meu-pv</p>
<p>kubectl apply -f pv-nfs.yaml</p>
<p>kubectl apply -f pvc.yaml</p>
<p>kubectl get pvc
<p>kubectl describe pvc meu-pvc</p>
<p>kubectl apply -f pod.yaml</p>
<p>kubectl describe pod nginx-pod</p>
