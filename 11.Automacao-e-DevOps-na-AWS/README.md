# ⚙️ Módulo 11 — Automação e DevOps na AWS

## 📘 Conteúdo do Módulo

1. **Como automatizar tarefas na AWS**
2. **Execução de tarefas automatizadas com AWS Lambda**
3. **Criação de recursos com Terraform e LocalStack**
4. **O que é DevOps**
5. **Aplicando DevOps na AWS (CI/CD)**
6. **Ferramentas AWS para DevOps**

---

## 🤖 Como Automatizar Tarefas na AWS

A automação permite simplificar e acelerar tarefas repetitivas, reduzindo erros humanos e aumentando a eficiência operacional.  
Na AWS, é possível automatizar desde infraestrutura até fluxos de trabalho complexos.

### 🔹 Ferramentas para Automação

| Ferramenta              | Função Principal                                                                 |
| ----------------------- | -------------------------------------------------------------------------------- |
| **AWS CloudFormation**  | Criação e gerenciamento de infraestrutura como código (IaC) usando JSON ou YAML. |
| **AWS Lambda**          | Execução de código sob demanda, sem gerenciamento de servidores.                 |
| **AWS CodePipeline**    | Automação do ciclo de vida de desenvolvimento (CI/CD).                           |
| **AWS Systems Manager** | Execução e gerenciamento de tarefas operacionais (patches, scripts, manutenção). |
| **AWS Step Functions**  | Orquestração de fluxos automatizados entre diferentes serviços AWS.              |

### 🔹 Formas de Automação

- **Infraestrutura como Código (IaC):** com **CloudFormation** ou **Terraform**.
- **Scripts e CLI:** via **AWS CLI** ou **SDKs** (Python, Node.js, Java, etc.).
- **Eventos Automatizados:** via **Lambda** e **EventBridge**.

### 🔹 Benefícios

- Redução de erros manuais.
- Aumento da velocidade de execução.
- Escalabilidade e repetibilidade.
- Liberação de tempo para tarefas estratégicas.

---

## 🪄 Executando Tarefas com AWS Lambda

O **AWS Lambda** é uma ferramenta serverless usada para automatizar execuções de código em resposta a eventos, sem precisar gerenciar infraestrutura.

### 🔹 Casos de Uso

- Processar arquivos enviados a um bucket S3.
- Disparar notificações em filas (SNS/SQS).
- Atualizar bancos de dados DynamoDB automaticamente.
- Criar integrações com APIs RESTful via API Gateway.

### 🔹 Benefícios

- Execução sob demanda.
- Escalabilidade automática.
- Custo sob uso: paga apenas pelo tempo de execução.
- Ideal para tarefas recorrentes e reativas.

---

## 🧱 Criação de Recursos com Terraform

O **Terraform**, da HashiCorp, é uma ferramenta de Infraestrutura como Código (IaC) que permite definir, provisionar e versionar infraestrutura AWS de forma declarativa.

### 🔹 O que Podemos Fazer

- Criar e atualizar recursos AWS como:
  - **VPCs**, **EC2**, **S3**, **Lambda**, **RDS**, etc.
- Automatizar mudanças em larga escala.
- Gerenciar dependências entre recursos.
- Versionar e aplicar reverter configurações de infraestrutura.

### 🔹 Benefícios

- Código reutilizável e modular.
- Provisionamento rápido e consistente.
- Integração com múltiplos provedores de nuvem (AWS, Azure, GCP).
- Redução de erros e controle de versões da infraestrutura.

---

### 🧩 AWS Local com LocalStack

O **LocalStack** é uma ferramenta open-source que permite simular a AWS localmente, facilitando o desenvolvimento e testes sem custos reais.

#### 🔹 Etapas

1. Instalar o LocalStack (CLI ou Desktop).
2. Criar recursos AWS localmente (S3, EC2, DynamoDB, etc.).
3. Testar chamadas via Postman, NoSQL Workbench e CLI.
4. Recriar e destruir recursos usando código Terraform (IaC).

🔗 **Documentação:** [https://docs.localstack.cloud](https://docs.localstack.cloud)

---

## 🧩 O que é DevOps?

O **DevOps** é uma metodologia que une desenvolvimento (Dev) e operações (Ops) para entregar software rapidamente e com qualidade.  
Ele busca colaboração, automação, integração contínua (CI) e entrega contínua (CD).

### 🔹 5 Princípios do DevOps

1. **Colaboração** entre times.
2. **Automação** de processos.
3. **Melhoria contínua**.
4. **Foco no cliente**.
5. **Planejamento orientado ao resultado final**.

### 🔹 CI/CD — Integração e Entrega Contínua

- **CI (Continuous Integration):**  
  Código é integrado e testado continuamente no repositório.
- **CD (Continuous Delivery/Deployment):**  
  Entrega e implantação automática de novas versões.

💡 **Objetivo:** Entregar novas funcionalidades com velocidade, consistência e segurança.

---

## 🧰 Aplicando DevOps na AWS

A AWS oferece um conjunto completo de ferramentas DevOps, cobrindo todas as etapas do pipeline de desenvolvimento.

### 🔹 Pipeline CI/CD — Exemplo Prático

| Etapa                   | Serviço AWS       | Função                                   |
| ----------------------- | ----------------- | ---------------------------------------- |
| **1️⃣ Commit do Código** | AWS CodeCommit    | Repositório Git gerenciado               |
| **2️⃣ Build/Testes**     | AWS CodeBuild     | Compila e executa testes automatizados   |
| **3️⃣ Implantação**      | AWS CodeDeploy    | Distribui o código em EC2, ECS ou Lambda |
| **4️⃣ Monitoramento**    | Amazon CloudWatch | Coleta logs, métricas e eventos          |
| **5️⃣ Auditoria**        | AWS CloudTrail    | Rastreia ações e mudanças                |

---

## 🧩 Ferramentas AWS para DevOps

| Ferramenta             | Função Principal                 |
| ---------------------- | -------------------------------- |
| **AWS CodeCommit**     | Controle de versão Git           |
| **AWS CodeBuild**      | Build e testes automatizados     |
| **AWS CodeDeploy**     | Implantação automatizada         |
| **AWS CodePipeline**   | Orquestração de CI/CD            |
| **AWS CloudFormation** | Infraestrutura como Código (IaC) |
| **Amazon CloudWatch**  | Monitoramento e logs             |
| **AWS IAM**            | Controle de identidade e acesso  |

🔗 [AWS DevOps Tools](https://aws.amazon.com/pt/devops/)

---

## 📊 Benefícios do DevOps na AWS

- **Entrega contínua:** ciclos curtos e ágeis de desenvolvimento.
- **Escalabilidade e automação:** ambientes replicáveis e controlados.
- **Menor tempo de deploy:** releases mais frequentes e sem downtime.
- **Monitoramento centralizado:** com CloudWatch e CloudTrail.
- **Menos erros e maior qualidade:** devido à automação e testes contínuos.
