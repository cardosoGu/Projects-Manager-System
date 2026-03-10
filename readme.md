
# Project Management API

API backend para gerenciamento de projetos com upload e download de arquivos `.zip`, controle de usuários e armazenamento em blob storage.

⚠️ **Código privado**
Este sistema foi desenvolvido para uma startup e o código fonte não pode ser divulgado publicamente por acordo de confidencialidade (NDA). Abaixo estão documentadas a arquitetura e as funcionalidades do sistema.

---

# Tecnologias utilizadas

- TypeScript
- Node.js
- Fastify / Express
- PostgreSQL
- Prisma ORM
- Blob Storage (S3 compatible)

---

# Objetivo do projeto

Criar uma API para permitir que usuários da plataforma possam:

- criar projetos
- enviar arquivos compactados (`.zip`)
- baixar arquivos posteriormente
- gerenciar seus próprios projetos
- permitir que administradores tenham controle global do sistema

O foco do backend foi **organização de dados, segurança de acesso e gerenciamento de arquivos**.

---

# Funcionalidades

## Autenticação e controle de acesso

O sistema possui separação de permissões entre:

- **Usuário**
- **Administrador**

Usuários acessam apenas seus próprios projetos, enquanto administradores possuem acesso completo ao sistema.

---

## Gerenciamento de projetos

A API permite:

- criação de projetos
- listagem de projetos
- visualização de detalhes
- exclusão de projetos

Cada projeto pode possuir arquivos associados.

---

## Upload de arquivos

Usuários podem enviar arquivos `.zip`, que são armazenados em um serviço de **blob storage compatível com S3**.

Fluxo simplificado:

```
Client
  ↓

API
  ↓

Validação do arquivo
  ↓

Upload para Blob Storage

  ↓
Registro no banco de dados

```

# Admin Routes

## create new project

![alt text](image-1.png)
![alt text](image.png)

## List Projects

![alt text](image-2.png)

## buscar projeto por ID

![alt text](image-3.png)

## Atualizar Projeto

![alt text](image-4.png)

## Upload .zip

![alt text](image-5.png)
![alt text]({050D87D8-1241-4088-9F0D-FDD0FA461516}.png)
![alt text]({C4B898E4-E31C-44BA-98DE-EB922014575E}.png)

## rota para admin fazer download de projeto

![alt text](image-6.png)

## Delete Project

![alt text](image-7.png)

## delete from blob

![alt text](image-8.png)
![alt text](image-9.png)

# User

## get personal projects (USER)

![alt text](image-10.png)

## user download personal project

![alt text](image-11.png)
