# Descomplicando o Kubernetes - Expert Mode

## DAY-4

### O que iremos ver hoje?

Hoje é dia de falar sobre dois objetos muito importantes no Kubernetes, os *ReplicaSets* e os *DaemonSets*.

Nós já sabemos o que é um Deployment e também já sabemos o que é um Pod no detalhe, então agora vamos conhecer essas duas figuras que estão super conectadas com o Deployment e com o Pod. Quando falamos sobre Deployment é impossível não falar sobre ReplicaSet, pois o Deployment é um objeto que cria um ReplicaSet e o ReplicaSet é um objeto que cria um Pod, veja que tudo está conectado.

Já o nosso querido DaemonSet é um objeto que cria um Pod e esse Pod é um objeto que fica rodando em todos os nodes do cluster, super importante para nós, pois é com DaemonSet que nós conseguimos garantir que teremos pelo menos um Pod rodando em cada node do cluster. Por exemplo, imagine que você precisa de instalar os agente do Datadog ou ainda um exporter do Prometheus em todos os nodes do cluster, para isso você precisa de um DaemonSet.

Ainda no dia de hoje, nós iremos aprender como garantir que os nossos Pods estão rodando corretamente, através das Probes do Kubernetes.

Nós vamos falar sobre Readiness Probe, Liveness Probe e Startup Probe, e claro, mostrando todos os detalhes em exemplos práticos e super explicativos.

Hoje é o dia de você aprender sobre esses dois objetos que são super importantes, e ainda, garantir que nós nunca colocaremos os nossos Pods em produção sem antes garantir que eles estão rodando corretamente e sendo checados pelas Probes do Kubernetes.




## Comandos utilizados

<p>kubectl apply -f nginx-deployment.yaml</p>
<p>ubectl get deployments</p>
<p>kubectl get replicasets</p>
<p>kubectl scale deployment nginx-deployment --replicas=3</p>
<p>kubectl describe deployment nginx-deployment</p>
<p>kubectl rollout undo deployment nginx-deployment</p>
<p>kubectl apply -f nginx-replicaset.yaml</p>
<p>kubectl get pods</p>
<p>kubectl describe replicaset nginx-replicaset</p>
<p>kubectl delete pod nginx-replicaset</p>
<p>kubectl get pods -o=jsonpath='{range .items[*]}{"\n"}{.metadata.name}{"\t"}{range .spec.containers[*]}{.image}{"\t"}{end}{end}'</p>
<p>kubectl get pods -o wide -l app=node-exporter</p>
<p>kubectl delete replicaset nginx-replicaset</p>
<p>kubectl delete -f nginx-replicaset.yaml</p>
<p>kubectl apply -f node-exporter-daemonset.yaml</p>
<p>kubectl get daemonset</p>
<p>kubectl get pods -l app=node-exporter</p>
<p>kubectl describe daemonset node-exporter</p>
<p>kubectl rollout status deployment/nginx-deployment</p>
<p>kubectl describe pod nginx-deployment</p>
<p>kubectl apply -f nginx-startup.yaml</p>
kubectl apply -f nginx-startup.yaml</p>
<p>kubectl apply -f nginx-todas-probes.yaml</p>








