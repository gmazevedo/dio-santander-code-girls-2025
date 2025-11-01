# 🗄️ Módulo 5 — Banco de Dados na AWS

## 📘 Conteúdo do Módulo

1. **Amazon RDS – Relational Database Service**
2. **Amazon DynamoDB – Banco de Dados NoSQL**
3. **Estratégias de Backup e Recuperação de Dados**

---

## ⚙️ Amazon RDS — Banco de Dados Relacional Gerenciado

O **Amazon RDS (Relational Database Service)** é um serviço de banco de dados relacional **totalmente gerenciado**, que facilita a configuração, operação e escalabilidade de bancos na nuvem.

### 🔹 Principais Características

- **Gerenciamento simplificado:** automação de tarefas como provisionamento, backup e patching.
- **Escalabilidade:** ajuste de capacidade conforme a demanda da aplicação.
- **Alta disponibilidade:** suporte a **Multi-AZ** e replicação.
- **Monitoramento:** integração com **Amazon CloudWatch**.
- **Custo sob demanda:** pague apenas pelo uso.

### 🔹 Benefícios

- Implantação rápida e segura.
- Desempenho otimizado com balanceamento automático.
- Flexibilidade para personalizar configurações.
- Redução do tempo de administração e manutenção.

### 🔹 Pontos de Atenção

- **Custos variáveis** conforme armazenamento e tráfego.
- **Complexidade** em ambientes corporativos com múltiplos bancos.

### 🔹 Casos de Uso

- **Aplicativos Web e Mobile:** bancos escaláveis e de alta disponibilidade.
- **Soluções Empresariais:** ERP, CRM e sistemas críticos.

### 🔹 Tipos de Bancos Compatíveis com RDS

| Banco                    | Descrição                                                 | Destaques                                            |
| ------------------------ | --------------------------------------------------------- | ---------------------------------------------------- |
| **Amazon Aurora**        | Compatível com MySQL e PostgreSQL                         | Até 5x mais rápido que MySQL; alta disponibilidade   |
| **Oracle**               | Suporte completo com licenciamento Bring-Your-Own-License | Automação de backups e patches                       |
| **Microsoft SQL Server** | Gerenciado nativamente                                    | Suporte a ferramentas nativas do SQL Server          |
| **MySQL**                | Código aberto amplamente utilizado                        | Compatível com aplicações legadas                    |
| **PostgreSQL**           | Objeto-relacional e extensível                            | Suporte a várias linguagens (PL/pgSQL, Python, etc.) |
| **MariaDB**              | Derivado do MySQL                                         | Ideal para quem busca independência de fornecedores  |

---

## ⚡ Amazon DynamoDB — Banco de Dados NoSQL

O **Amazon DynamoDB** é um banco de dados **NoSQL totalmente gerenciado**, que oferece **baixa latência** e **escalabilidade automática**, ideal para aplicações modernas e distribuídas.

### 🔹 Principais Características

- **Sem servidor:** não requer gerenciamento de infraestrutura.
- **Escalabilidade automática:** ajusta a capacidade conforme a demanda.
- **Desempenho constante:** respostas rápidas, mesmo sob grandes cargas.
- **Suporte a dados não estruturados e semiestruturados.**
- **Integração nativa com serviços AWS (Lambda, API Gateway, etc.).**

### 🔹 Estrutura de Dados

- **Tabelas:** organizam os dados em registros.
- **Chave primária (Partition Key ou Sort Key):** define a estrutura de indexação.
- **Atributos:** campos que armazenam dados em formatos flexíveis (JSON, texto, números, listas).

### 🔹 Casos de Uso

- Aplicações que requerem **baixa latência e alta escalabilidade**, como:
  - **Netflix:** histórico de visualização.
  - **Airbnb:** dados de reservas e propriedades.
  - **Lyft:** controle de viagens em tempo real.
  - **Dropbox:** gerenciamento de metadados.

### 🔹 Benefícios

- Altamente disponível e confiável.
- Ideal para grandes volumes de dados.
- Rápida integração com pipelines de dados e APIs.
- Custos proporcionais ao uso.

---

## 🔁 Estratégias de Backup e Recuperação de Dados

O backup é essencial para garantir **continuidade operacional** e **proteção contra falhas**, desastres e perda de informações.

### 🔹 O que é um Backup?

É a **cópia dos dados e configurações** de um sistema, armazenada separadamente do ambiente principal, com o objetivo de recuperação em caso de falhas, incidentes ou desastres.

---

### 🔹 Importância do Backup

- Prevenção contra **falhas de sistema** e **erros humanos**.
- **Continuidade de negócios** em caso de desastres.
- **Conformidade** com auditorias e legislações.
- **Redução de custos** e impactos em incidentes críticos.

---

### 🔹 Etapas para Definir uma Estratégia de Backup

1. **Avaliação e Planejamento**

   - Identificar **dados críticos** a serem protegidos.
   - Definir **RPO (Recovery Point Objective)** e **RTO (Recovery Time Objective)**.
     - **RPO:** quanto de dado pode ser perdido entre backups.
     - **RTO:** tempo máximo aceitável para restaurar o sistema.

2. **Seleção de Serviços AWS**

   - **Amazon S3:** armazenamento de backups com políticas de ciclo de vida.
   - **AWS Backup:** gerencia e automatiza backups de serviços AWS.
   - **Amazon RDS Automated Backups e Snapshots:** backup automatizado e restauração pontual.
   - **Amazon DynamoDB On-Demand Backup:** backups sob demanda e **PITR (Point-In-Time Recovery)**.

3. **Implementação**

   - **Backups automáticos e incrementais.**
   - **Replicação entre regiões (S3 Cross-Region Replication).**
   - **Automação com AWS Lambda** e **monitoramento com CloudWatch.**

4. **Recuperação e Testes**

   - Testar regularmente a **restauração de dados**.
   - Simular falhas com exercícios de **Backup Drill**.

5. **Segurança e Conformidade**

   - Criptografia em trânsito (TLS) e em repouso (S3 Server-Side Encryption).
   - Controle de acesso com **IAM Policies**.
   - Auditoria e logs via **AWS CloudTrail**.

6. **Custo e Otimização**
   - Usar **AWS Cost Explorer** para análise e controle de custos.
   - Aplicar **políticas de ciclo de vida** para mover dados entre classes de armazenamento.
   - Balancear custo x retenção de dados conforme o negócio.

🔗 [Planejamento de Recuperação – AWS Well-Architected Framework](https://docs.aws.amazon.com/pt_br/wellarchitected/latest/reliability-pillar/rel_planning_for_recovery_disaster_recovery.html)
