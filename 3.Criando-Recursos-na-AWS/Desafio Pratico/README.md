# 🚀 Desafio Prático — Website no Amazon S3

Um exercício prático para consolidar os aprendizados sobre S3, Git e hospedagem web.

### 🔹 Requisitos

- Instalar o Git Bash: [git-scm.com/download](https://git-scm.com/download)
- Clonar o repositório do site:

  ```bash
  git clone https://github.com/alexsandrolechner/website-formacao-aws

  ```

- Editar o código HTML:
- Inserir sua foto, nome e biografia.
- Adicionar links para redes sociais e contatos.
- Personalizar o layout conforme desejar.

### 🔹 Publicação

1. Criar o bucket no Amazon S3.
2. Fazer o upload dos arquivos HTML, CSS e imagens.
3. Aplicar as políticas de acesso público.

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

4. Ativar Static Website Hosting.
5. Testar o site acessando o endpoint gerado.

### 🔗 Referências

- [AWS S3 Website Hosting Guide](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/EnableWebsiteHosting.html)
- [AWS Lambda Documentation](https://docs.aws.amazon.com/pt_br/lambda/latest/dg/welcome.html)
- [Código do Website](https://github.com/alexsandrolechner/website-formacao-aws)
