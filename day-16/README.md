
# Descomplicando o Kubernetes - Expert Mode

## DAY-16

### O que iremos ver hoje?

Hoje é dia de falar sobre Taints, Tolerations, Affinity e Antiaffinity. Vamos entender como eles podem nos ajudar no dia-a-dia na administração de um cluster Kubernetes.

Com eles podemos isolar workloads, garantir que Pods sejam agendados em Nodes específicos e até mesmo evitar que Pods sejam agendados em determinados Nodes do cluster.

## Comandos utilizados

<p>kubectl get nodes</p>
<p>kubectl taint nodes kind-worker key=value:NoSchedule</p>
<p>kubectl describe node kind-worker</p>
<p>kubectl create deployment nginx --image=nginx --replicas=10</p>
<p>kubectl taint nodes kind-worker key=value:NoSchedule-</p>
<p>kubectl rollout restart deployment nginx</p>
<p>kubectl get pods -o wide</p>
<p>kubectl taint nodes kind-worker2 gpu=true:NoSchedule</p>
<p>kubectl rollout restart deployment nginx</p>
<p>kubectl create deployment nginx --image=nginx --replicas=5 --dry-run=client -o yaml > gpu-deployment.yaml</p>
<p>kubectl apply -f gpu-deployment.yaml</p>
<p>kubectl taint nodes kind-worker2 gpu=true:NoSchedule-</p>
<p>kubectl label nodes kind-worker2 gpu=true</p>
<p>kubectl apply -f gpu-deployment3.yaml</p>



