# 🧰 Módulo 3 — Criando Nossos Recursos (Hands-On)

## 📘 Conteúdo do Módulo

1. **Amazon EC2 – Criação de Instâncias na Nuvem**
2. **Amazon S3 – Armazenamento e Hospedagem de Sites**
3. **Amazon Lambda – Funções Serverless**
4. **Desafio Prático – Publicação de Website no Amazon S3**

---

## ⚙️ Amazon EC2 — Criando Sua Primeira Instância

O **Amazon EC2 (Elastic Compute Cloud)** é o serviço de **máquinas virtuais** da AWS.  
Neste módulo, o aluno cria e configura uma instância EC2 para compreender os principais componentes de um ambiente de computação na nuvem.

### 🔹 Etapas do Hands-On

1. **Acessar o Console AWS → EC2 → Launch Instance.**
2. **Escolher a AMI (Amazon Machine Image)**: Linux ou Windows.
3. **Selecionar o tipo de instância:** definir CPU e memória conforme o caso de uso.
4. **Configurar armazenamento (EBS)** e regras de rede (Security Groups).
5. **Gerar e baixar a chave SSH (.pem)** para acesso remoto.
6. **Conectar à instância** usando SSH (Linux/Mac) ou PuTTY (Windows).

### 💡 Objetivo

- Compreender o modelo **IaaS (Infraestrutura como Serviço)**.
- Criar uma instância funcional e acessível pela internet.
- Entender na prática os conceitos de provisionamento, rede e segurança.

---

## 🗄️ Amazon S3 — Armazenamento e Hospedagem

O **Amazon S3 (Simple Storage Service)** é um serviço de **armazenamento de objetos** que também pode hospedar sites estáticos.

### 🔹 Conceitos Aplicados

- Criação de **buckets** para armazenar arquivos e páginas.
- Configuração de **políticas de acesso público** e **permissões IAM**.
- Entendimento do conceito de **URL de objeto (endpoint)**.
- Introdução à hospedagem de sites estáticos com S3.

### 🧰 Etapas do Hands-On

1. Criar um **bucket** no S3 e ativar a opção **“Block all public access – OFF”**.
2. Configurar a **Bucket Policy** para permitir leitura pública:

   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Sid": "PublicReadGetObject",
         "Effect": "Allow",
         "Principal": "*",
         "Action": "s3:GetObject",
         "Resource": "arn:aws:s3:::SEU_BUCKET/*"
       }
     ]
   }
   ```

3. Fazer upload dos arquivos do site (HTML, CSS, imagens).
4. Ativar a opção de website hosting e copiar o endpoint público gerado.

### 💡 Objetivo

- Entender o funcionamento do armazenamento em nuvem.
- Aplicar práticas de segurança e versionamento.
- Publicar um website pessoal hospedado no Amazon S3.

## 🧠 Amazon Lambda — Computação Serverless

O AWS Lambda é um serviço de computação serverless, onde o desenvolvedor executa código sem precisar gerenciar servidores.

### 🔹 Conceito de Serverless

- Serverless ≠ Sem Servidor: há servidores, mas a AWS os gerencia automaticamente.
- O foco é apenas no código da aplicação, não na infraestrutura.
- Pagamento é feito apenas pelo tempo de execução e quantidade de invocações.

### 🧩 Diferença EC2 x Lambda

| Característica | **EC2**                     | **Lambda**                 |
| -------------- | --------------------------- | -------------------------- |
| Modelo         | IaaS (Infraestrutura)       | FaaS (Função como Serviço) |
| Gerenciamento  | Usuário gerencia servidores | AWS gerencia tudo          |
| Escalabilidade | Manual ou automática        | Totalmente automática      |
| Custos         | Baseado em tempo ligado     | Baseado em execuções       |
| Ideal para     | Aplicações contínuas        | Eventos e automações       |

## 🧰 Hands-On: Criando um “Hello World”

1. Acessar AWS Lambda → Create Function → Author from scratch.
2. Definir nome da função e runtime (ex: Python 3.9).
3. Inserir o código:

```python
   def lambda_handler(event, context):
   return "Hello, World from AWS Lambda!"
```

4. Salvar e testar com um evento de exemplo.
5. Observar a execução e o log gerado no Amazon CloudWatch.

### 💡 Objetivo

- Aprender o ciclo completo de criação e execução de uma função Lambda.
- Entender a arquitetura event-driven e o conceito pay-per-use.
- Demonstrar a agilidade do modelo serverless para automações e APIs.
