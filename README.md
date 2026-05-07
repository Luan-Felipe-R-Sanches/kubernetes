# ☸️ Laboratório Prático de Kubernetes

Este repositório contém uma vasta coleção de manifestos YAML utilizados para estudar e demonstrar os principais recursos e objetos do Kubernetes.
O conteúdo foi organizado de forma progressiva e pedagógica, facilitando a aprendizagem desde os conceitos mais básicos até os mais avançados.

---

# 📁 Estrutura do Laboratório (Passo a Passo)

## 1️⃣ Fundamentos e Configurações Básicas

### `01_namespaces/`

Isolamento e organização lógica dos recursos do cluster.

### `02_pods/`

A menor unidade computacional do Kubernetes.
Exemplos: Redis, Tomcat, Nginx.

### `03_liveness-probes/`

Verificações de saúde (*health checks*) para garantir que os containers reiniciem quando estiverem indisponíveis.

### `04_gerenciamento-recursos/`

Definição de:

* `requests` → mínimo garantido de CPU/Memória
* `limits` → limite máximo de consumo

---

## 2️⃣ Controladores de Carga de Trabalho (Workloads)

### `05_deployment/`

Gerenciamento de réplicas e atualizações de aplicações (*Rolling Updates*).

### `06_daemonset/`

Garante que um Pod execute em todos (ou em alguns) nós do cluster.

### `07_jobs/`

Execução de tarefas efémeras até à conclusão.

### `08_cronjob/`

Execução de tarefas recorrentes utilizando agendamentos no formato cron.

---

## 3️⃣ Comunicação e Rede

### `09_services/`

Exposição de aplicações utilizando:

* `ClusterIP`
* `NodePort`
* `LoadBalancer`

### `10_endpoints/`

Mapeamentos diretos para IPs de Pods ou serviços externos ao cluster.

### `11_endpointslices/`

Escalonamento de Endpoints para clusters maiores, melhorando a performance de rede.

---

## 4️⃣ Configuração e Persistência

### `12_volumes/`

Persistência de dados utilizando:

* `emptyDir`
* `hostPath`

### `13_configmap/`

Injeção de variáveis de ambiente e ficheiros de configuração nas aplicações.

### `14_secrets/`

Gestão de dados sensíveis:

* Passwords
* Tokens
* Certificados

### `15_statefulsets/`

Workloads *stateful*, ideais para bases de dados e aplicações que exigem:

* Persistência
* Identidade de rede estável
* Ordem de inicialização

---

## 5️⃣ Segurança e Projeto Final

### `16_rbac/`

Configuração de permissões com:

* `Roles`
* `RoleBindings`
* `ServiceAccounts`

### `99_projeto-pratico/`

Projeto final do laboratório:
Deployment completo de um ambiente **Jupyter Notebook** isolado em um Namespace dedicado.

---

# 🚀 Como Utilizar

## Pré-requisitos

Antes de iniciar, certifique-se de possuir:

* Kubernetes Cluster local:

  * Minikube
  * Kind
  * Docker Desktop

* Ferramentas instaladas:

  * `kubectl`
  * Docker

---

## 1️⃣ Clonar o Repositório

```bash
git clone <url-do-seu-repositorio>
cd kubernetes
```

---

## 2️⃣ Aplicar os Manifestos

### Exemplo: Projeto Final do Jupyter Notebook

#### Criar o Namespace

```bash
kubectl apply -f 99_projeto-pratico/jupyter-ns.yaml
```

#### Criar o Deployment

```bash
kubectl apply -f 99_projeto-pratico/jupyter-dp.yaml
```

---

## 3️⃣ Verificar os Recursos

```bash
kubectl get all -n jupyter
```

---

# 🛠️ Tecnologias Abordadas

* Kubernetes (K8s)
* Docker / Containers
* Linux Kube-Tools (`kubectl`)

## Aplicações utilizadas nos exemplos

* Nginx
* Apache HTTPD
* Tomcat
* Redis
* MariaDB / MySQL
* Jupyter Minimal Notebook

---

# 📚 Objetivo do Projeto

Este laboratório foi desenvolvido com foco em:

* Estudos práticos de Kubernetes
* Aprendizagem progressiva
* Administração de clusters
* Deploy de aplicações containerizadas
* Networking e segurança em Kubernetes

---

# 👨‍💻 Autor

Projeto desenvolvido e mantido por **Luan Felipe**.
