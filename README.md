# Guia de Exemplos: Recursos Básicos do Kubernetes

Este guia oferece um resumo dos passos para criar e gerenciar recursos básicos no Kubernetes, abordando Pods, ReplicaSets, Deployments e Services.

## 1. Criar um Pod

Um **Pod** é a unidade básica de execução em Kubernetes. Um Pod pode conter um ou mais containers que compartilham o mesmo espaço de rede e armazenamento. 

**Passos:**
- Crie um Pod especificando a imagem do container e a porta a ser exposta.
- O Pod é a base para os recursos mais avançados, como ReplicaSets e Deployments.

## 2. Criar um ReplicaSet

Um **ReplicaSet** garante que um número especificado de réplicas de um Pod esteja sempre em execução, mesmo se um Pod falhar.

**Passos:**
- Defina o número desejado de réplicas.
- Use um seletor para identificar quais Pods devem ser gerenciados pelo ReplicaSet.
- O ReplicaSet cria e mantém os Pods necessários para atingir o número de réplicas desejado.

## 3. Criar um Deployment

Um **Deployment** gerencia a criação e atualização de Pods e ReplicaSets, garantindo que a versão desejada dos Pods esteja sempre em execução.

**Passos:**
- Defina o número desejado de réplicas de Pods.
- Configure o Deployment para atualizar automaticamente os Pods e ReplicaSets conforme necessário.
- O Deployment é útil para gerenciar versões e rollouts de aplicações.

## 4. Criar um Service

Um **Service** expõe Pods para a rede interna ou externa e facilita o balanceamento de carga.

**Passos:**
- Escolha o tipo de Service, como `LoadBalancer` para expor o Service externamente.
- Use um seletor para associar o Service aos Pods que ele deve balancear.
- Configure as portas expostas para permitir o acesso aos containers nos Pods.

## Conclusão

Esses são os recursos básicos do Kubernetes e suas funções essenciais. Cada um desempenha um papel crucial na gestão e operação de aplicações em um cluster Kubernetes. Para mais detalhes, consulte a [documentação oficial do Kubernetes](https://kubernetes.io/docs/home/).

# Setando Alias para facilitar algumas repetições

## No Bash (ex: Git Bash, WSL, etc.)

### 1. Abrir o arquivo de configuração:
```bash
nano ~/.bashrc

```

### 2. Adicionar os Alias:
```bash
alias t='terraform'
alias ta='terraform apply'
alias ti='terraform init'
alias tp='terraform plan'
alias td='terraform destroy'
alias tf='terraform fmt'
alias tv='terraform validate'
alias tu='terraform output'
alias tstate='terraform state'
alias tgraph='terraform graph'

alias k='kubectl'
alias ka='kubectl apply -f'
alias kex='kubectl exec -i -t'
alias klo='kubectl logs -f'
alias kp='kubectl proxy'
alias kg='kubectl get'
alias kd='kubectl describe'
alias krm='kubectl delete'
alias kgpo='kubectl get pods'
alias kdpo='kubectl describe pods'
```

### 3. Salvar e sair:
- Pressione Ctrl + O para salvar o arquivo.
- Pressione Enter para confirmar.
- Pressione Ctrl + X para sair do editor.

### 4. Aplicar as mudanças:
- Agora, recarregue o arquivo de configuração executando:
```bash
source ~/.bashrc
```


## No PowerShell (Windows)
### 1. Abrir o perfil do PowerShell:

```PowerShell 
notepad $PROFILE
```

### 2. Adicionar os Alias:
```PowerShell 
Set-Alias k kubectl
Set-Alias ka 'kubectl apply -f'
Set-Alias kex 'kubectl exec -i -t'
Set-Alias klo 'kubectl logs -f'
Set-Alias kp 'kubectl proxy'
Set-Alias kg 'kubectl get'
Set-Alias kd 'kubectl describe'
Set-Alias krm 'kubectl delete'
Set-Alias kgpo 'kubectl get pods'
Set-Alias kdpo 'kubectl describe pods'

Set-Alias t 'terraform'
Set-Alias ta 'terraform apply'
Set-Alias ti 'terraform init'
Set-Alias tp 'terraform plan'
Set-Alias td 'terraform destroy'
Set-Alias tf 'terraform fmt'
Set-Alias tv 'terraform validate'
Set-Alias tu 'terraform output'
Set-Alias tstate 'terraform state'
Set-Alias tgraph 'terraform graph'

```
### 3. Salvar e fechar:
- Salve o arquivo no Bloco de Notas e feche.

### 4. Permitir a execução de scripts (se necessário):
```PowerShell 
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser

```