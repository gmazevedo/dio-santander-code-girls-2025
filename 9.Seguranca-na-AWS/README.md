# 🔐 Módulo 9 — Segurança na AWS

## 📘 Conteúdo do Módulo

1. **Práticas Recomendadas de Segurança na Nuvem**
2. **Criptografia de Dados na AWS**
3. **AWS WAF — Firewall de Aplicativos da Web**

---

## 🛡️ Práticas Recomendadas de Segurança na Nuvem

A segurança na AWS é estruturada sobre o Modelo de Responsabilidade Compartilhada, que define as fronteiras entre o que é responsabilidade da AWS e o que é responsabilidade do usuário.

### 🔹 Modelo de Responsabilidade Compartilhada

| Responsável | Escopo de Responsabilidade                                                                        |
| ----------- | ------------------------------------------------------------------------------------------------- |
| **AWS**     | Segurança **da nuvem** — infraestrutura global, data centers, hardware, software base e rede.     |
| **Usuário** | Segurança **na nuvem** — configurações, gerenciamento de acesso, criptografia e políticas de uso. |

### 🔹 Exemplos Práticos

- **Amazon EC2 (Infraestrutura):**  
  O usuário é responsável por manter o sistema operacional atualizado, aplicar patches, configurar firewalls e gerenciar chaves SSH.

- **Amazon S3 (Serviço Gerenciado):**  
  A AWS gerencia a infraestrutura, mas o usuário deve configurar políticas de acesso, controle de permissões e criptografia para evitar exposição pública dos dados.

---

### 🔹 Pilares de Segurança no AWS Well-Architected Framework

O pilar de segurança dentro do AWS Well-Architected Framework cobre as principais áreas para uma arquitetura segura:

1. **Gerenciamento de Identidade e Acesso:**  
   Aplicar o princípio do menor privilégio, utilizando o AWS IAM para controlar permissões de forma granular.

2. **Proteção de Dados:**  
   Criptografar informações em repouso e em trânsito com o uso do AWS KMS.

3. **Resposta a Incidentes:**  
   Utilizar **AWS CloudTrail** para auditoria e detecção de atividades suspeitas.

4. **Segurança da Infraestrutura:**  
   Empregar serviços como **AWS Shield** e **AWS WAF** para proteção contra ataques DDoS e ameaças externas.

---

## 🔒 Criptografia de Dados na AWS

A criptografia é fundamental para garantir a confidencialidade e a integridade dos dados, tanto em repouso quanto em trânsito.

### 🔹 Criptografia em Repouso

Protege os dados armazenados em serviços como:

- **Amazon S3:** objetos criptografados automaticamente antes de serem gravados.
- **Amazon RDS:** bancos de dados protegidos com chaves gerenciadas.
- **Amazon EBS:** volumes criptografados em nível de bloco.

#### 🧩 AWS Key Management Service (KMS)

O **AWS KMS** é o serviço que gerencia as chaves de criptografia usadas nos diferentes serviços da AWS.  
Ele oferece:

- Criação, rotação e exclusão de chaves.
- Controle de acesso granular via IAM Policies.
- Integração com S3, RDS, EBS, DynamoDB e outros serviços.

---

### 🔹 Criptografia em Trânsito

Protege os dados durante a transmissão, evitando interceptações e adulterações.  
Utiliza protocolos como TLS (Transport Layer Security) para garantir a segurança das comunicações entre clientes, servidores e serviços AWS.

---

### 🔹 Gerenciamento de Segredos

#### **AWS Secrets Manager**

Gerencia credenciais sensíveis e segredos (como senhas, tokens e chaves de API).

**Principais funcionalidades:**

- Armazenamento seguro e centralizado de segredos.
- Rotação automática de credenciais, reduzindo riscos de vazamento.
- Integração com bancos de dados, APIs e aplicações serverless.
- Evita armazenar senhas diretamente no código-fonte.

#### **AWS CloudHSM (Hardware Security Module)**

Permite gerenciar chaves de criptografia com hardware dedicado, atendendo a requisitos de segurança corporativos e regulatórios.  
Exemplo: suporte à assinatura digital e criptografia de mensagens para sistemas financeiros como o PIX.

🔗 [Exemplo: Arquitetura com AWS CloudHSM para o PIX (AWS Blog Brasil)](https://aws.amazon.com/pt/blogs/aws-brasil/arquitetura-com-aws-cloudhsm-para-suportar-assinatura-digital-e-transmissao-segura-de-mensagens-ao-pix/)

---

## 🧱 AWS WAF — Web Application Firewall

O **AWS WAF** é um firewall de aplicativos da web que protege sites e aplicações hospedadas na AWS contra ataques e acessos maliciosos.

### 🔹 Como Funciona

O WAF atua como uma camada de filtragem entre o usuário e a aplicação, analisando o tráfego HTTP/HTTPS e bloqueando solicitações suspeitas.

### 🔹 Integrações

Funciona em conjunto com:

- **Amazon CloudFront (CDN)**
- **Application Load Balancer (ALB)**  
  Essas integrações ajudam a distribuir o tráfego e proteger a aplicação em múltiplos níveis.

---

### 🔹 Regras e Proteções

O AWS WAF permite criar regras personalizadas para permitir ou bloquear tráfego com base em padrões específicos.

| Tipo de Proteção                 | Descrição                                                                |
| -------------------------------- | ------------------------------------------------------------------------ |
| **Bots e Scrapers**              | Bloqueia IPs que acessam honeypots (URLs iscas).                         |
| **Injeção de SQL**               | Analisa URLs, cabeçalhos e corpo HTML para detectar comandos maliciosos. |
| **Cross-Site Scripting (XSS)**   | Impede scripts que possam comprometer o navegador do usuário.            |
| **Scanners e Probes**            | Monitora logs via AWS Lambda e bloqueia comportamentos suspeitos.        |
| **Listas Brancas/Negras de IPs** | Define manualmente IPs confiáveis ou bloqueados.                         |
| **Atacantes Conhecidos**         | Integra-se a listas de reputação de IPs de terceiros.                    |
| **Ataques HTTP Flood (DDoS)**    | Limita requisições por IP para evitar sobrecarga de servidores.          |

---

### 🧰 Implementação Prática (POC)

- **Arquivo de teste:** `WAF_TESTES.txt`
- Utilização de **CloudFormation** para automatizar a configuração do WAF e gerar URLs honeypot para testes.
