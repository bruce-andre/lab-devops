# lab-devops
# 🚀 lab-devops

Laboratório para projetos de DevOps

---

## 📌 Projeto

Plataforma Kubernetes Multi-Cluster com GitOps

---

## 🎯 Objetivo

Implementar um ambiente completo com múltiplos clusters Kubernetes, seguindo boas práticas de:

- Automação  
- Segurança  
- Observabilidade  
- GitOps  

---

## 🧱 Arquitetura

### 🔹 Clusters Kubernetes

- **DEV** (Desenvolvimento)  
- **HOMOL** (Homologação)  
- **PROD** (Produção)  

### 🔹 Estrutura de cada cluster

- 1 **Control Plane**  
- 2 **Worker Nodes**  

---

## 🗺️ Diagrama da Arquitetura
                    +----------------------+
                    |      GitHub Repo     |
                    |   (Source of Truth)  |
                    +----------+-----------+
                               |
                               v
                      +--------+--------+
                      |     Argo CD     |
                      |   (GitOps CD)   |
                      +--------+--------+
                               |
    ---------------------------------------------------------
    |                         |                            |
    v                         v                            v
    |                         |                            |
    ---------------------------------------------------------
                               |
                               v
    +-----------------------------------------------------+
    | Rancher | Grafana | Harbor | Vault | Backstage      |
    +-----------------------------------------------------+

    
---

## 🔄 GitOps

- **Argo CD** → responsável pela entrega contínua  
- **GitHub** → repositório central (*source of truth*)  

### 🔁 Fluxo

1. Alteração no repositório GitHub  
2. Argo CD detecta mudança  
3. Sincroniza automaticamente com o cluster  
4. Aplicação é atualizada  

---

## 📊 Monitoramento

- **Grafana** para visualização de métricas  

---

## 📦 Armazenamento de Imagens

- **Harbor** como registry privado de imagens Docker  

---

## 🧩 Gerenciamento de Clusters

- **Rancher** para gerenciamento centralizado dos clusters Kubernetes  

---

## 🔐 Gerenciamento de Segredos

- **Vault** para armazenamento seguro de secrets  

---

## 🛠️ Developer Portal

- **Backstage** para centralizar:

  - Serviços  
  - Documentação  
  - Workflows de desenvolvimento  

---

## 🌍 Infraestrutura como Código

- **Terraform** para provisionamento e automação da infraestrutura  

## 📁 Estrutura do Projeto

```bash
lab-devops/
├── terraform/          # Provisionamento da infraestrutura (IaC)
├── clusters/           # Configuração dos clusters Kubernetes
│   ├── dev/            # Ambiente de desenvolvimento
│   ├── homol/          # Ambiente de homologação
│   └── prod/           # Ambiente de produção
│
├── argocd/             # Configurações e aplicações do Argo CD (GitOps)
├── apps/               # Manifests Kubernetes / Helm charts
├── platform/           # Serviços da plataforma (Grafana, Vault, Harbor, etc)
│
└── README.md
