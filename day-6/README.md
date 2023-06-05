# Descomplicando o Kubernetes - Expert Mode

## DAY-6

### O que iremos ver hoje?

Durante o dia de hoje nós vamos aprender tudo sobre volumes, hoje é o dia de você finalmente descomplicar os volumes no Kubernetes! \o/

Hojel nós iremos entender e configurar o que é um configmap, um persistente volume (PV) e um persistent volume claim (PVC)! E para isso iremos utilizar como exemplo diferentes tipos de clusters Kubernetes! Calma, eu explico melhor!

Para ajudar no nosso aprendizado sobre volumes, vamos utlizar diferentes clusters Kubernetes! Vamos ter exemplos utilizando EKS, kind e instâncias em cloud providers.

Então fique ciente de que hoje é o dia onde você irá descomplicar volumes no Kubernetes! #VAIIII.

## Comandos utilizados

kubectl get storageclass
kubectl describe storageclass standard
kubectl apply -f storageclass.yaml
kubectl describe storageclass giropops
kubectl get pv -A
kubectl apply -f pv.yaml
kubectl get pv
kubectl describe pv meu-pv
kubectl apply -f pv-nfs.yaml
kubectl apply -f pvc.yaml
kubectl get pvc
kubectl describe pvc meu-pvc
kubectl apply -f pod.yaml
kubectl describe pod nginx-pod
