# 🧭 Módulo 7 — Serviços Intermediários e Avançados (AWS Cloud Foundations)

## 📘 Conteúdo do Módulo

1. **AWS Lambda**  
2. **Amazon ECS e EKS**  
3. **Amazon SNS e SQS**  
4. **AWS Step Functions**

---

## ⚙️ AWS Lambda — Computação Serverless

O **AWS Lambda** é um serviço de computação **serverless** que executa código em resposta a eventos, sem necessidade de gerenciar servidores.

### 🔹 Características
- **Execução sob demanda:** cobra apenas pelo tempo de execução do código.  
- **Escalonamento automático:** dimensiona automaticamente conforme o número de eventos.  
- **Gerenciamento automatizado:** provisionamento, manutenção e logging feitos pela AWS.  
- **Alta disponibilidade:** infraestrutura redundante e resiliente.  
- **Custo:** cerca de **US$ 0,20 por 1 milhão de requisições**.

### 🧩 Benefícios
- Reduz custos operacionais.  
- Aumenta agilidade no desenvolvimento.  
- Facilita integração com outros serviços AWS (S3, DynamoDB, SNS, etc.).  
- Ideal para workloads event-driven e microsserviços.

---

## 🐳 Amazon ECS e EKS — Contêineres Gerenciados

Serviços voltados à **orquestração de contêineres**, essenciais para arquiteturas baseadas em **microserviços**.

### 🔹 Amazon ECS (Elastic Container Service)
- Serviço gerenciado de **orquestração de contêineres Docker**.  
- Permite criar e escalar aplicações em contêineres com segurança e integração AWS.

#### Principais Recursos:
- **Gerenciamento simples:** automação do cluster.  
- **Escalabilidade automática:** ajusta contêineres conforme demanda.  
- **Integração nativa:** IAM, VPC, CloudWatch, entre outros.  
- **Segurança:** controle de acesso granular.

#### Caso de uso:
Cada parte de um aplicativo (ex: catálogo, carrinho, pagamentos) roda em um contêiner independente, com **tarefas e serviços** definidos no ECS.

> **ECR (Elastic Container Registry):** serviço complementar para armazenar e gerenciar imagens Docker.

O **ECS** é recomendado para workloads **moderados** ou equipes iniciando com contêineres.

---

### 🔹 Amazon EKS (Elastic Kubernetes Service)
Serviço **gerenciado de Kubernetes (K8s)** que permite executar e escalar contêineres sem manter infraestrutura própria.

#### Benefícios:
- Gestão automatizada do cluster Kubernetes.  
- Escalonamento dinâmico baseado na carga de trabalho.  
- Alta compatibilidade com workloads multicloud e híbridos.  
- Ideal para **ambientes corporativos complexos** já baseados em Kubernetes.

#### Diferenças ECS x EKS
| Aspecto | **ECS** | **EKS** |
|----------|----------|----------|
| Orquestrador | Proprietário AWS | Kubernetes (open source, Google) |
| Complexidade | Baixa/Média | Alta |
| Casos ideais | Iniciantes em contêineres | Empresas maduras em microsserviços |
| Backend | AWS Fargate (serverless) | Kubernetes clusters gerenciados |
| Personalização | Limitada | Ampla |

---

## 💬 Amazon SNS e SQS — Mensageria e Notificações

### 🔹 Amazon SNS (Simple Notification Service)
Serviço **assíncrono** de **notificações entre aplicações e usuários**.

#### Recursos:
- Modelo **Pub/Sub (Publicador → Assinante)**.  
- Tipos de tópicos:
  - **Padrão:** maior throughput, entrega possivelmente fora de ordem.  
  - **FIFO:** garante ordem e entrega única (limite de ~300 msg/s).  
- Integração com **Lambda**, **SQS**, **e-mails**, **SMS** e **push notifications**.

Usado para **notificações instantâneas e broadcast** de mensagens.

---

### 🔹 Amazon SQS (Simple Queue Service)
Serviço **de filas de mensagens** que desacopla componentes de sistemas distribuídos.

#### Características:
- Tipos de filas: **Padrão** e **FIFO**.  
- Mensagens ficam invisíveis após leitura por tempo configurável (visibility timeout).  
- **Amortece picos de tráfego**, garantindo processamento constante.  

Usado para **comunicação entre sistemas** e processamento assíncrono de dados.

#### SNS x SQS
| Aspecto | **SNS** | **SQS** |
|----------|----------|----------|
| Modo de envio | Broadcast (1:N) | Fila (P2P) |
| Ideal para | Notificações instantâneas | Processamento assíncrono |
| Ordem de mensagens | Padrão ou FIFO | FIFO opcional |
| Integração comum | Lambda, SQS | Lambda, EC2 |

---

## 🔁 AWS Step Functions

O **AWS Step Functions** é um serviço totalmente gerenciado que coordena vários serviços AWS em fluxos de trabalho visuais.  
Com ele, é possível encadear funções Lambda, tarefas ECS, chamadas de API e integrações com SQS, DynamoDB, SNS e muitos outros serviços.

### 🔹 Conceito
Cada fluxo de trabalho é chamado de **State Machine** (máquina de estados) e é definido em **Amazon States Language (ASL)**, um formato JSON que descreve:
- A sequência das etapas,  
- As condições de transição entre estados,  
- O tratamento de erros e exceções,  
- E as ações tomadas em cada etapa.

Um fluxo pode conter etapas sequenciais, paralelas, condicionais ou com loops.

### 🔹 Tipos de Step Functions
- **Standard Workflows:** projetadas para execuções de longa duração e alta durabilidade.  
- **Express Workflows:** ideais para execuções curtas, de alta taxa e baixo custo (ex: eventos em tempo real).

---

### 🧰 Como Configurar uma Step Function

1. **Acesse o Console AWS → Step Functions.**
   - Clique em **Create state machine**.

2. **Escolha o tipo de máquina de estados:**
   - *Standard* (processos longos) ou *Express* (processos rápidos).

3. **Defina o fluxo no formato JSON (Amazon States Language):**
   Exemplo simples:
   ```json
   {
     "Comment": "Exemplo de Step Function com duas funções Lambda",
     "StartAt": "ValidaDados",
     "States": {
       "ValidaDados": {
         "Type": "Task",
         "Resource": "arn:aws:lambda:us-east-1:123456789012:function:ValidaDados",
         "Next": "ProcessaDados"
       },
       "ProcessaDados": {
         "Type": "Task",
         "Resource": "arn:aws:lambda:us-east-1:123456789012:function:ProcessaDados",
         "End": true
       }
     }
   }

4. Configure as permissões (IAM Role):

- A Step Function precisa ter permissão para executar os serviços envolvidos (ex: Lambda, SQS, ECS).

5. Salve e execute a State Machine.

- Você pode acompanhar a execução em tempo real, visualizar logs e analisar falhas diretamente no console.

### 🔹 Benefícios do Step Functions

- Coordenação visual: fluxos de trabalho facilmente compreensíveis.
- Recuperação automática: tratamento de erros e reprocessamento.
- Escalabilidade e resiliência: totalmente gerenciado e integrado ao ecossistema AWS.
- Custo baseado em transições: paga-se apenas pelas etapas executadas.

