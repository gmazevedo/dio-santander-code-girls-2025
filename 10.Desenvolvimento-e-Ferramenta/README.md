# 💻 Módulo 10 — Desenvolvimento e Ferramentas

## 📘 Conteúdo do Módulo

1. **AWS SDKs e AWS CLI — Ferramentas de desenvolvimento e linha de comando**
2. **AWS CloudFormation — Automação de infraestrutura como código**
3. **AWS CodeDeploy — Implantação automatizada de aplicações**

---

## 🧰 AWS SDKs e AWS CLI — Ferramentas de Desenvolvimento

A AWS oferece duas principais formas de interação com seus serviços: via SDKs (Software Development Kits) e via CLI (Command Line Interface).  
Essas ferramentas permitem que desenvolvedores e administradores criem, gerenciem e automatizem recursos da AWS de forma programática.

---

## 🔹 AWS SDK — Desenvolvimento Integrado

O **AWS SDK** permite interagir com os serviços da AWS usando a linguagem de programação de sua escolha, facilitando a integração com aplicações.

#### 🧩 Linguagens e Comandos de Instalação

| Linguagem   | Comando                                                                             |
| ----------- | ----------------------------------------------------------------------------------- |
| **Node.js** | `npm install @aws-sdk/client-s3 --save`                                             |
| **Python**  | `pip install boto3`                                                                 |
| **Java**    | `Maven: <dependency>` / `Gradle: implementation 'software.amazon.awssdk:s3:2.20.0'` |
| **.NET**    | `dotnet add package AWSSDK.S3`                                                      |
| **Ruby**    | `gem install aws-sdk-s3`                                                            |
| **PHP**     | `composer require aws/aws-sdk-php`                                                  |
| **Go**      | `go get github.com/aws/aws-sdk-go-v2`                                               |

#### 💡 Benefícios

- Permite desenvolver aplicações diretamente integradas à AWS.
- Suporte a múltiplas linguagens e ambientes de desenvolvimento.
- Ideal para automação e integração contínua (CI/CD).

---

## 🔹 AWS CLI — Linha de Comando

O **AWS CLI (Command Line Interface)** é uma ferramenta que permite gerenciar a AWS via terminal ou scripts automatizados.

#### 🧭 Características

- Ideal para administradores e equipes DevOps.
- Facilita a execução de tarefas rápidas, como criação de buckets S3, execução de instâncias EC2 ou consultas a logs.
- Comando para verificar a versão instalada:
  ```bash
  aws --version
  ```

## 🧩 Comparação entre AWS SDK e CLI

| Aspecto                   | **AWS SDK**                       | **AWS CLI**                    |
| ------------------------- | --------------------------------- | ------------------------------ |
| **Interface**             | Código (linguagem de programação) | Linha de comando               |
| **Público-alvo**          | Desenvolvedores                   | Administradores / DevOps       |
| **Linguagens Suportadas** | Python, Java, C#, Node.js etc.    | Nenhuma                        |
| **Complexidade**          | Exige conhecimento em programação | Mais simples, comandos diretos |
| **Automação**             | Ideal para fluxos complexos       | Ideal para tarefas repetitivas |

## 🧱 AWS CloudFormation — Automação de Infraestrutura como Código (IaC)

O AWS CloudFormation é uma ferramenta que automatiza a criação e o gerenciamento de infraestrutura na AWS usando templates declarativos (JSON ou YAML).

### 🔹 Benefícios

- Infraestrutura como Código (IaC): define recursos como EC2, S3, VPC e RDS em arquivos.
- Automação Total: cria, atualiza e exclui ambientes de forma consistente.
- Padronização: garante configurações idênticas em múltiplos ambientes (dev, stage, prod).

#### 💡 Exemplo de uso:

Provisionar automaticamente uma arquitetura completa com rede, instâncias EC2 e bancos de dados RDS a partir de um único template YAML.

## ⚙️ AWS CodeDeploy — Implantação Automatizada de Aplicações

O AWS CodeDeploy é um serviço que automatiza o processo de implantação (deploy) de aplicações em ambientes AWS e on-premises.

### 🔹 O que é e Como Funciona

Pense no CodeDeploy como uma esteira automatizada:
Você fornece o código no início do processo e o serviço o distribui automaticamente para todos os servidores (EC2, instâncias locais ou containers) de forma segura e sem interrupções.

### 🔹 Benefícios

1. Automação de Implantação
   - Elimina etapas manuais e reduz erros humanos.
   - Permite implantações simultâneas em várias instâncias.
2. Velocidade e Eficiência
   - Acelera o lançamento de novas versões e correções.
   - Facilita processos de CI/CD com integração contínua.
3. Alta Disponibilidade e Escalabilidade
   - Integra-se com Elastic Load Balancer e Auto Scaling.
   - Garante disponibilidade mesmo durante picos de tráfego.
4. Integração com Outros Serviços AWS
   - Amazon EC2: implantação direta em instâncias.
   - Amazon S3: armazenamento e versionamento do pacote de aplicação.
   - Elastic Load Balancing: balanceamento automático de tráfego durante o deploy.

#### 💡 Exemplo Prático

Imagine uma aplicação web em execução em diversas instâncias EC2.
O CodeDeploy pode distribuir uma nova versão do aplicativo automaticamente em todas elas, garantindo:

- Atualização uniforme
- Zero downtime
- Rastreabilidade do processo
