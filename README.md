# Implementando Minha Primeira Stack com AWS CloudFormation  

Este repositório faz parte do **Desafio da DIO - Formação AWS Cloud Practitioner**, com o objetivo de criar e gerenciar recursos na **AWS** utilizando o **AWS CloudFormation**.

Mesmo sem acesso à conta AWS, toda a estrutura, o template e os conceitos foram aplicados de forma simulada, mostrando o entendimento completo do processo.  

---

## Objetivo do Desafio  
- Entender o que é o AWS CloudFormation  
- Aprender a escrever templates YAML  
- Simular a criação de uma Stack  
- Documentar o processo e aprendizados  

---

## O que é o AWS CloudFormation  
O **CloudFormation** é um serviço da AWS que permite criar e gerenciar infraestrutura como código (IaC).  
Isso significa que, em vez de criar manualmente cada recurso na AWS, você descreve tudo em um arquivo YAML ou JSON, e a AWS faz o resto automaticamente.  

**Vantagens:**
- Automação da infraestrutura  
- Padrão e consistência entre ambientes  
- Facilidade para replicar recursos  
- Controle por versionamento no GitHub  

---

## Template Criado  
O arquivo abaixo (`main-stack.yaml`) foi criado para representar uma Stack simples com um **Bucket S3** privado.  

## Validação do Template

Caso tivesse acesso à AWS CLI configurada, o comando para validar o template seria:

```bash
aws cloudformation validate-template --template-body file://templates/main-stack.yaml


```yaml
AWSTemplateFormatVersion: '2010-09-09'
Description: Stack de exemplo para o desafio DIO - Implementando sua primeira Stack com CloudFormation.

Resources:
  MeuBucketS3:
    Type: AWS::S3::Bucket
    Properties:
      BucketName: meu-primeiro-bucket-cloudformation-brendajuliao
      AccessControl: Private
