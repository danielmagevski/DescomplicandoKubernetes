# Descomplicando o Kubernetes - Expert Mode

## DAY-2

### O que iremos ver hoje?

Durante a aula de hoje, iremos ver todos os detalhes importantes sobre o menor objeto do Kubernetes, o Pod.
Vamos ver desde a criação de um simples Pod, passando por Pod com multicontainers, com volumes e ainda com limitação ao consumo de recursos, como CPU ou memória.
E claro, vamos aprender como ver todos os detalhes de um Pod em execução e brincar bastante com nossos arquivos YAML.

## Comandos utilizados

kubectl run giropops --image=nginx --port=80
kubectl get pods
kubectl get pods --all-namespaces
kubectl get pods -A
kubectl get pods -n <namespace>
kubectl get pods -n kube-system
kubectl get pods <nome-do-pod> -o yaml
kubectl get pods giropops -o yaml
kubectl get pods <nome-do-pod> -o json
kubectl get pods giropops -o json
kubectl get pods <nome-do-pod> -o wide
kubectl get pods giropops -o wide
kubectl describe pods giropops
kubectl delete pods giropops
kubectl logs giropops
kubectl logs -f giropops
kubectl attach giropops -c strigus
kubectl exec giropops -c strigus -it -- sh
kubectl exec giropops -c strigus -- ls
kubectl exec -it ubuntu -- bash

