# Descomplicando o Kubernetes - Expert Mode

## DAY-8

### O que iremos ver hoje?

Hoje é dia de falar sobre duas coisas super importantes no mundo do Kubernetes, hoje nós vamos falar sobre *Secrets* e *ConfigMaps*.

Sim, essas duas peças fundamentais para que você possa ter a sua aplicação rodando no Kubernetes da melhor forma possível, pois elas são responsáveis por armazenar as informações sensíveis da sua aplicação, como por exemplo, senhas, tokens, chaves de acesso, configurações, etc.

Depois do dia de hoje você vai entender como funciona o armazenamento de informações sensíveis no Kubernetes e como você pode fazer para que a sua aplicação possa consumir essas informações da melhor forma possível.

O que são Secrets?

Os Secrets fornecem uma maneira segura e flexível de gerenciar informações sensíveis, como senhas, tokens OAuth, chaves SSH e outros dados que você não quer expor nas configurações de seus aplicaçãos.

Um Secret é um objeto que contém um pequeno volume de informações sensíveis, como uma senha, um token ou uma chave. Essas informações podem ser consumidas por Pods ou usadas pelo sistema para realizar ações em nome de um Pod.

 

Como os Secrets funcionam

Os Secrets são armazenados no Etcd, o armazenamento de dados distribuído do Kubernetes. Por padrão, eles são armazenados sem criptografia, embora o Etcd suporte criptografia para proteger os dados armazenados nele. Além disso, o acesso aos Secrets é restrito por meio de Role-Based Access Control (RBAC), o que permite controlar quais usuários e Pods podem acessar quais Secrets.

Os Secrets podem ser montados em Pods como arquivos em volumes ou podem ser usados para preencher variáveis de ambiente para um container dentro de um Pod. Quando um Secret é atualizado, o Kubernetes não atualiza automaticamente os volumes montados ou as variáveis de ambiente que se referem a ele.

 

Tipos de Secrets

Existem vários tipos de Secrets que você pode usar, dependendo de suas necessidades específicas. Abaixo estão alguns dos tipos mais comuns de Secrets:

Opaque Secrets - são os Secrets mais simples e mais comuns. Eles armazenam dados arbitrários, como chaves de API, senhas e tokens. Os Opaque Secrets são codificados em base64 quando são armazenados no Kubernetes, mas não são criptografados. Eles podem ser usados para armazenar dados confidenciais, mas não são seguros o suficiente para armazenar informações altamente sensíveis, como senhas de banco de dados.

kubernetes.io/service-account-token - são usados para armazenar tokens de acesso de conta de serviço. Esses tokens são usados para autenticar Pods com o Kubernetes API. Eles são montados automaticamente em Pods que usam contas de serviço.

kubernetes.io/dockercfg e kubernetes.io/dockerconfigjson - são usados para armazenar credenciais de registro do Docker. Eles são usados para autenticar Pods com um registro do Docker. Eles são montados em Pods que usam imagens de container privadas.

kubernetes.io/tls, kubernetes.io/ssh-auth e kubernetes.io/basic-auth - são usados para armazenar certificados TLS, chaves SSH e credenciais de autenticação básica, respectivamente. Eles são usados para autenticar Pods com outros serviços.

bootstrap.kubernetes.io/token - são usados para armazenar tokens de inicialização de cluster. Eles são usados para autenticar nós com o plano de controle do Kubernetes.

Tem mais alguns tipos de Secrets, mas esses são os mais comuns. Você pode encontrar uma lista completa de tipos de Secrets na documentação do Kubernetes.

Cada tipo de Secret tem um formato diferente. Por exemplo, os Secrets Opaque são armazenados como um mapa de strings, enquanto os Secrets TLS são armazenados como um mapa de strings com chaves adicionais para armazenar certificados e chaves, por isso é importante saber qual tipo de Secret você está usando para que você possa armazenar os dados corretamente.

Antes de criar um Secret, o Base64

Antes de começarmos a criar os nossos Secrets, precisamos entender o que é o Base64, pois esse é um assunto que sempre gera muitas dúvidas e sempre está presente quando falamos de Secrets.

Primeira coisa, Base64 é criptografia? Não, Base64 não é criptografia, Base64 é um esquema de codificação binária para texto que visa garantir que os dados binários possam ser enviados por canais que são projetados para lidar apenas com texto. Esta codificação ajuda a garantir que os dados permaneçam intactos sem modificação durante o transporte.

Base64 está comumente usado em várias aplicações, incluindo e-mail via MIME, armazenamento de senhas complexas, e muito mais.

A codificação Base64 converte os dados binários em uma string de texto ASCII. Essa string contém apenas caracteres que são considerados seguros para uso em URLs, o que torna a codificação Base64 útil para codificar dados que estão sendo enviados pela Internet.

No entanto, a codificação Base64 não é uma forma de criptografia e não deve ser usada como tal. Em particular, ela não fornece nenhuma confidencialidade. Qualquer um que tenha acesso à string codificada pode facilmente decodificá-la e recuperar os dados originais. Entender isso é importante para que você não armazene informações sensíveis em um formato codificado em Base64, pois isso não é seguro.

Agora que você já sabe o que é o Base64, vamos ver como podemos codificar e decodificar uma string usando o Base64.

Para codificar uma string em Base64, você pode usar o comando base64 no Linux. Por exemplo, para codificar a string giropops em Base64, você pode executar o seguinte comando:

echo -n 'giropops' | base64
 

O comando acima irá retornar a string Z2lyb3BvcHM=.

Para decodificar uma string em Base64, você pode usar o comando base64 novamente, mas desta vez com a opção -d. Por exemplo, para decodificar a string Z2lyb3BvcHM= em Base64, você pode executar o seguinte comando:

echo -n 'Z2lyb3BvcHM=' | base64 -d
 

O comando acima irá retornar a string giropops, simples como voar!

Estou usando o parâmetro -n no comando echo para que ele não adicione uma nova linha ao final da string, pois isso pode causar problemas ao codificar e decodificar a string.

Pronto, acho que você já está pronto para criar os seus Secrets, então é hora de começar a brincar!

## Comandos utilizados

<p>echo -n 'giropops' | base64</p>
<p>echo -n 'Z2lyb3BvcHM=' | base64 -d</p>
<p>kubectl create -f giropops-secret.yaml</p>
<p>kubectl get secret giropops-secret</p>
<p>kubectl get secret giropops-secret -o yaml</p>
<p>kubectl describe secret giropops-secret</p>
<p>kubectl create secret generic giropops-secret --from-literal=username=<SEGREDO> --from-literal=password=giropops</p>
<p>kubectl apply -f giropops-pod.yaml</p>
<p>kubectl get pods</p>
<p>kubectl exec giropops-pod -- env</p>
<p>kubectl apply -f dockerhub-secret.yaml</p>
<p>openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout chave-privada.key -out certificado.crt</p>
<p>kubectl create secret tls meu-servico-web-tls-secret --cert=certificado.crt --key=chave-privada.key</p>
<p>kubectl get secret meu-servico-web-tls-secret -o yaml</p>
<p>kubectl create configmap nginx-config --from-file=nginx.conf</p>
<p>kubectl apply -f nginx-config.yaml</p>
<p>kubectl get configmap nginx-config -o yaml</p>
<p>kubectl apply -f nginx.yaml</p>
<p>kubectl get pods</p>
<p>kubectl expose pod nginx</p>
<p>kubectl get services</p>
<p>kubectl port-forward service/nginx 4443:443</p>
<p>curl -k https://localhost:4443</p>