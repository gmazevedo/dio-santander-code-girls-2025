# ☁️ Módulo 1 — Introdução à AWS e Conceitos Básicos (AWS Cloud Foundations)

## 📘 Conteúdo do Módulo

1. **Visão Geral da AWS** – História, modelo de negócios e infraestrutura global
2. **Conceitos Fundamentais** – Regiões, zonas de disponibilidade e serviços gerenciados
3. **Configuração da Conta AWS** – Criação e boas práticas de segurança
4. **Hands-On** – IAM, CLI, automação e controle de gastos

---

## 🏛️ História da AWS

A **Amazon Web Services (AWS)** é o braço de computação em nuvem da Amazon, lançada em **2006**.  
A empresa, fundada em **1994 por Jeff Bezos**, começou como uma **livraria online** e rapidamente se transformou em um ecossistema tecnológico global.

O nome _Amazon_ foi escolhido em referência ao **rio Amazonas**, o maior do mundo — representando a ideia de grandeza e alcance global.

A AWS nasceu da necessidade de **fornecer infraestrutura escalável** e **serviços sob demanda**, transformando a maneira como empresas e desenvolvedores criam soluções digitais.

---

## 🌎 Infraestrutura Global da AWS

A AWS possui uma das maiores e mais seguras infraestruturas de nuvem do mundo.

### 🔹 Estrutura

- **Regiões (Regions):**  
  Áreas geográficas que agrupam diversos datacenters próximos fisicamente.
- **Zonas de Disponibilidade (Availability Zones):**  
  Conjuntos de datacenters independentes dentro de uma região, conectados entre si com alta velocidade e redundância.

Atualmente, a AWS conta com:

- **33 regiões geográficas**
- **105 zonas de disponibilidade (AZs)**
- Planos anunciados para novas regiões na **Alemanha, Malásia, Nova Zelândia e Tailândia**.

🔗 [Infraestrutura Global da AWS](https://aws.amazon.com/pt/about-aws/global-infrastructure)

---

## 💼 Modelo de Negócio da AWS

O modelo da AWS é baseado no conceito **“pay-as-you-go”** — pague apenas pelo que usar.

### 🔹 Características do Modelo Cloud

- **OPEX (Operational Expenditure):**  
  Custos operacionais conforme o consumo.
- **CAPEX (Capital Expenditure):**  
  Modelo tradicional de investimento fixo em infraestrutura física.

A AWS elimina a necessidade de altos investimentos iniciais, permitindo que qualquer empresa inicie um projeto de forma escalável e econômica.

### 🔹 Variedade de Serviços

A AWS oferece mais de **200 serviços** ativos, cobrindo:

- Computação (EC2, Lambda)
- Armazenamento (S3, EBS)
- Bancos de Dados (RDS, DynamoDB)
- Machine Learning, IoT, Big Data e muito mais

---

## 🧩 Modelos de Computação em Nuvem

| Modelo   | Nome                        | Responsabilidade do Usuário                       | Exemplo AWS              |
| -------- | --------------------------- | ------------------------------------------------- | ------------------------ |
| **IaaS** | Infraestrutura como Serviço | Controle de servidores, rede, armazenamento e SO  | EC2                      |
| **PaaS** | Plataforma como Serviço     | Foco no desenvolvimento; sem gestão de servidores | Elastic Beanstalk        |
| **SaaS** | Software como Serviço       | Uso direto de aplicações via internet             | AWS WorkMail, Salesforce |

Cada modelo oferece diferentes níveis de **controle, flexibilidade e gerenciamento**.

---

## 🧠 Conceitos Fundamentais

- **Regiões:** locais físicos distribuídos globalmente.
- **AZs:** múltiplos datacenters redundantes dentro de uma mesma região.
- **Edge Locations:** pontos de presença usados por serviços como CloudFront para reduzir latência.
- **Serviços Gerenciados:** infraestrutura e manutenção feita pela AWS, permitindo ao usuário focar na aplicação.

---

## 🛡️ Configuração da Conta AWS e Práticas de Segurança

Durante o módulo, o aluno cria sua própria conta AWS e aprende as boas práticas de segurança essenciais para um ambiente em nuvem.

### 🔹 Requisitos para Criação de Conta

- E-mail válido
- Número de telefone
- Cartão de crédito (para verificação e ativação)

### 🔹 Boas Práticas de Segurança

1. **Proteger a conta root** e usá-la apenas para tarefas administrativas.
2. **Ativar MFA (Autenticação Multifator)** para evitar acessos indevidos.
3. **Criar usuários e grupos com permissões específicas (IAM)**.
4. **Monitorar cobranças e alertas de gastos.**
5. **Nunca compartilhar credenciais de acesso.**

🔗 [Melhores práticas IAM – Documentação AWS](https://docs.aws.amazon.com/pt_br/IAM/latest/UserGuide/best-practices.html)

---

## 💻 Hands-On — Prática Guiada

### 🔸 1. Controle de Gastos e Alertas

- Criação de **orçamentos e notificações automáticas** via AWS Billing & Cost Management.

### 🔸 2. IAM — Identidade e Acesso

- Criação de **usuários, grupos e políticas de permissão**.
- Automação via script `bash scriptIAM.sh usuarios.csv` para gerar múltiplos usuários com AWS CLI.

### 🔸 3. Formas de Acesso

- **Console AWS:** interface gráfica da plataforma.
- **AWS CLI (Command Line Interface):** automação via terminal.
- **CloudShell:** ambiente de linha de comando integrado ao navegador.
