# 🧭 Módulo 8 — Gerenciamento e Governança na AWS

## 📘 Conteúdo do Módulo

1. **Amazon CloudWatch** – Monitoramento e métricas
2. **AWS CloudTrail** – Auditoria e rastreamento de atividades
3. **AWS Identity and Access Management (IAM)** – Controle de acesso e segurança
4. **AWS Policies e Roles** – Políticas e papéis de permissão
5. **AWS CloudFormation** – Automação de infraestrutura
6. **AWS Well-Architected Framework** – Melhores práticas de arquitetura na AWS
7. **AWS CAF (Cloud Adoption Framework)** – Estrutura para adoção estratégica da nuvem

---

## 🔍 Amazon CloudWatch — Monitoramento em Tempo Real

O **Amazon CloudWatch** é o serviço responsável por monitorar recursos e aplicações em tempo real dentro da AWS.  
Ele coleta métricas, logs e eventos, permitindo criar alertas automáticos e dashboards personalizados para visualização do desempenho.

### 🔹 Funcionalidades Principais

- **Coleta de métricas** de serviços como EC2, RDS, S3 e Lambda.
- **Criação de alarmes:** define limites e envia notificações quando métricas são violadas.
- **Dashboards customizados:** monitoramento visual de aplicações e infraestrutura.
- **Integração com AWS Lambda:** permite ações automáticas em resposta a eventos.
- **CloudWatch Logs e Events:** coleta logs de aplicações e permite reagir a mudanças no estado de recursos.

### 🔹 Exemplos de Uso

- Monitorar uso de CPU e disco em instâncias EC2.
- Criar alarmes para iniciar novas instâncias quando a carga aumentar.
- Registrar operações de API em buckets S3.

💡 **Integração com o CloudTrail:**  
O CloudWatch pode ser configurado para registrar e visualizar eventos rastreados pelo CloudTrail.

---

## 🧾 AWS CloudTrail — Auditoria e Rastreamento

O **AWS CloudTrail** é um serviço de auditoria e conformidade que registra todas as ações realizadas em sua conta AWS.

### 🔹 O que ele faz

- Registra quem executou uma ação, quando e em qual recurso.
- Monitora eventos realizados via:
  - **Console AWS**
  - **AWS CLI**
  - **APIs**
- Gera logs detalhados armazenados em S3, podendo ser visualizados no CloudWatch.

### 🔹 Diferença entre CloudTrail e CloudWatch

| Serviço        | Finalidade                                                 |
| -------------- | ---------------------------------------------------------- |
| **CloudWatch** | Monitora métricas e gera alertas em tempo real.            |
| **CloudTrail** | Registra histórico de ações para auditoria e conformidade. |

### 🔹 Benefícios

- Auditoria completa de usuários e serviços.
- Detecção de acessos indevidos.
- Conformidade com normas de segurança e governança.

---

## 🧑‍💼 AWS Identity and Access Management (IAM)

O **AWS IAM** é o serviço que gerencia identidades, permissões e acessos dentro da AWS.  
Ele é essencial para garantir segurança, conformidade e eficiência operacional em ambientes de qualquer porte.

### 🔹 Principais Recursos

- **Usuários:** contas individuais com credenciais próprias.
- **Grupos:** conjuntos de usuários com permissões compartilhadas.
- **Roles (Funções):** identidades temporárias com permissões específicas, usadas por serviços ou aplicações.
- **Policies (Políticas):** definem o que cada usuário, grupo ou função pode fazer.

### 🔹 Benefícios

- Controle de acesso granular a todos os recursos da AWS.
- Aplicação de políticas de segurança consistentes.
- Integração com autenticação multifator (MFA).
- Fundamentação para Zero Trust Security.

### 🧰 Hands-On

1. Instalar **Git Bash** e **AWS CLI**.
2. Criar usuários programáticos com **Access Key** e **Secret Key**.
3. Configurar o **AWS CLI** com `aws configure`.

---

## 🔐 AWS Policies e Roles — Controle Granular de Permissões

As **Policies** (políticas) são documentos em formato **JSON** que definem as permissões de acesso a recursos da AWS.  
As **Roles** (funções) são identidades que assumem essas permissões para executar tarefas específicas.

### 🔹 Estrutura de uma Policy (Exemplo)

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "ListObjectsInBucket",
      "Effect": "Allow",
      "Action": ["s3:ListBucket"],
      "Resource": ["arn:aws:s3:::bucket-name"]
    },
    {
      "Sid": "AllObjectActions",
      "Effect": "Allow",
      "Action": "s3:*Object",
      "Resource": ["arn:aws:s3:::bucket-name/*"]
    }
  ]
}
```

### 🔹 Tipos de Policies

- **Identity Policy:** aplicada a usuários, grupos ou roles.
- **Resource Policy:** anexada diretamente ao recurso (ex: bucket S3).

Essas políticas garantem controle total sobre ações e recursos, reforçando a governança de segurança.

## 🏗️ AWS CloudFormation — Automação de Infraestrutura

O AWS CloudFormation permite criar, gerenciar e versionar ambientes completos na nuvem usando templates declarativos (YAML/JSON).

### 🔹 Benefícios

- **Automatização:** elimina a necessidade de criação manual de recursos.
- **Padronização:** garante que todos os ambientes sejam configurados de forma idêntica.
- **Integração:** compatível com quase todos os serviços AWS.

💡 Exemplo: criar automaticamente uma VPC, sub-redes, instâncias EC2 e regras de segurança com um único arquivo de configuração.

## 🧱 AWS Well-Architected Framework — Melhores Práticas

O Well-Architected Framework é o conjunto de pilares e princípios criados pela AWS para ajudar arquitetos a projetar sistemas eficientes e seguros.

### 🔹 Os 6 Pilares

1. **Excelência Operacional**
2. **Segurança**
3. **Confiabilidade**
4. **Eficiência de Performance**
5. **Otimização de Custos**
6. **Sustentabilidade**

💡 Ferramentas como o AWS Well-Architected Tool ajudam a avaliar e melhorar continuamente a arquitetura de seus sistemas.

## ☁️ AWS CAF — Cloud Adoption Framework

O AWS Cloud Adoption Framework (CAF) é uma metodologia para guiar empresas na migração e adoção da nuvem AWS.

### 🔹 Estrutura do CAF

O framework se baseia em 6 perspectivas principais:
| Perspectiva | Foco Principal |
| -------------- | ---------------------------------------- |
| **Business** | Estratégia e objetivos de negócio |
| **People** | Desenvolvimento e capacitação de equipes |
| **Governance** | Políticas, controle e conformidade |
| **Platform** | Infraestrutura e automação |
| **Security** | Proteção de dados e identidades |
| **Operations** | Manutenção, monitoramento e suporte |

O CAF fornece uma rota estruturada e segura para adoção da nuvem, garantindo eficiência e governança corporativa.
