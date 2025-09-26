# Serverless Contact App
# 📇 Serverless Contact App

En enkel **serverless applikation** byggd på AWS som låter dig spara och hämta kontakter.  
Projektet använder **DynamoDB, Lambda och API Gateway** för backend, och en enkel HTML-fil som frontend.

---

## ⚡ Arkitektur
- **DynamoDB** – lagrar kontakter (`id`, `name`, `email`)
- **AWS Lambda** – två funktioner:
  - `SaveContactFunction` (POST) – sparar en ny kontakt
  - `GetContactsFunction` (GET) – hämtar alla kontakter
- **API Gateway** – exponerar REST API med `/contact`
- **HTML + JavaScript** – enkel frontend som anropar API:et

---

## 📦 Deployment (CloudFormation)

### 1. Skapa stacken
Kör följande kommando i projektmappen:

```bash
aws cloudformation deploy \
  --template-file serverless-contact.yaml \
  --stack-name ServerlessContactApp \
  --capabilities CAPABILITY_IAM
