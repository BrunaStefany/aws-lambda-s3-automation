

## 🧭 **1. Estrutura do Projeto**

Crie um repositório no GitHub com o nome:

```
aws-lambda-s3-automation

```

---

## 🧾 **2. Modelo de README.md (principal entregável)**

Aqui está um modelo completo para você preencher com base na sua prática:

---

# 🚀 Automação de Tarefas com AWS Lambda e S3

## 🧠 **Descrição do Projeto**

Este projeto foi desenvolvido como parte do desafio da DIO **“Executando Tarefas Automatizadas com AWS Lambda e S3”**, com o objetivo de praticar e consolidar conhecimentos sobre **funções Lambda, gatilhos S3 e automação em nuvem**.

A proposta consiste em criar uma automação que é executada automaticamente quando um arquivo é enviado para um bucket S3, utilizando uma função Lambda para processar o evento.

---

## 🎯 **Objetivos de Aprendizagem**

* Entender o funcionamento do **AWS Lambda** e sua integração com o **S3**.
* Criar **funções automatizadas** que executam tarefas em resposta a eventos.
* Documentar o processo técnico de forma clara e reprodutível.
* Utilizar o **GitHub** como ferramenta de versionamento e portfólio técnico.

---

## ⚙️ **Arquitetura da Solução**

A arquitetura desenvolvida segue o fluxo abaixo:

```
Upload de arquivo no Bucket S3  →  Disparo do evento  →  Execução automática da Lambda Function
```

📸 *(adicione aqui a imagem do seu diagrama da AWS ou do console Lambda)*

---

## 🧩 **Componentes Utilizados**

| Serviço             | Função                            |
| ------------------- | --------------------------------- |
| **Amazon S3**       | Armazenamento e evento de disparo |
| **AWS Lambda**      | Execução automática de código     |
| **CloudWatch Logs** | Monitoramento e logs da função    |
| **IAM Role**        | Permissões seguras para execução  |

---

## 💻 **Código Exemplo (lambda_function.py)**

```python
import boto3
import json

def lambda_handler(event, context):
    s3 = boto3.client('s3')
    
    # Extrai informações do evento
    bucket = event['Records'][0]['s3']['bucket']['name']
    key = event['Records'][0]['s3']['object']['key']

    print(f"Arquivo {key} foi enviado para o bucket {bucket}!")

    # Aqui você pode adicionar uma ação, ex: copiar, converter ou registrar algo
    return {
        'statusCode': 200,
        'body': json.dumps(f"Processamento concluído para {key}")
    }
```

---

## 🪄 **Passos para Execução**

1. Criar um bucket no **Amazon S3**
2. Criar uma **função Lambda**

   * Runtime: Python 3.9 (ou superior)
   * Permissões: acesso ao S3
3. Criar um **gatilho (Trigger)** do tipo **S3 → Lambda**

   * Evento: `ObjectCreated`
4. Fazer upload de um arquivo no bucket e verificar os logs no **CloudWatch**
5. Confirmar que a função foi executada automaticamente ✅

---

## 🧠 **Insights e Aprendizados**

Durante a execução do projeto, aprendi:

* A importância do **IAM Role** para garantir segurança e permissões adequadas.
* Como o **S3 Event Notification** dispara automaticamente funções sem necessidade de servidores.
* Que logs do **CloudWatch** são essenciais para depuração e monitoramento.
* A integração entre Lambda e S3 facilita **pipelines serverless** simples e eficazes.

---

## 📚 **Referências e Recursos**

* [Documentação AWS Lambda](https://docs.aws.amazon.com/lambda/)
* [Documentação Amazon S3](https://docs.aws.amazon.com/s3/)
* [CloudFormation - S3 Object Lambda Example](https://docs.aws.amazon.com/AmazonS3/latest/userguide/transforming-objects.html)
* [Guia Markdown GitHub](https://www.markdownguide.org/basic-syntax/)
* [Formação AWS DIO](https://www.dio.me/)

---

## 👩‍💻 **Autora**

**Bruna Stefany**
📍 Projeto prático da [DIO - Digital Innovation One](https://www.dio.me/)
💬 *“Automatizar é libertar tempo para criar soluções melhores.”*

---





