# API REST para Controle de Usuários

## Descrição

Este projeto consiste em uma API REST desenvolvida com **Typescript**, **ExpressJS** e **PrismaORM**, utilizando um banco de dados relacional (**SQLite**) para gerenciar uma tabela de usuários. A API implementa as operações CRUD e inclui rotas para criação, leitura, atualização e exclusão de usuários. Também oferece recursos adicionais para busca de usuários por diferentes critérios.

## Funcionalidades Implementadas

### Requisitos Obrigatórios

- **Rota para criar usuário:**
  - Cria um novo usuário, garantindo que o **email** seja único.
  
- **Rota para retornar usuário por ID:**
  - Busca um usuário específico pelo ID.

- **Rota para retornar usuário por email:**
  - Busca um usuário específico pelo email.

- **Rota para retornar usuários por nome:**
  - Busca um ou mais usuários com base no nome.

- **Rota para deletar usuário por ID:**
  - Remove um usuário do banco de dados pelo ID.

- **Rota para atualizar usuário por ID:**
  - Atualiza as informações de um usuário pelo ID, garantindo que o **email** seja único.

### Campos Obrigatórios para Usuários

A tabela de usuários inclui os seguintes campos:

- **Id:** Identificador único.
- **Nome:** Nome do usuário.
- **Email:** Email único.
- **Senha:** Senha do usuário.
- **Idade:** Idade do usuário.
- **Estado:** Estado onde o usuário reside.
- **Cidade:** Cidade onde o usuário reside.

### Requisitos Opcionais

- **Docker:** A API pode ser configurada e executada localmente usando Docker.
- **Mensagens de erro personalizadas:**
  - Usuário não encontrado (em todas as rotas por ID e Email).
  - Email já existente (na criação e atualização de usuários).
- **Autenticação JWT:**
  - Rota de login e logout com geração de token JWT.
  - Validação de token para proteger as outras rotas.

## Tecnologias Utilizadas

- **Node.js**: Ambiente de execução.
- **ExpressJS**: Framework para desenvolvimento de APIs.
- **PrismaORM**: Gerenciador de banco de dados.
- **SQLite**: Banco de dados relacional.
- **Typescript**: Linguagem para maior segurança e tipagem estática.
- **Docker** (opcional): Para containerização da aplicação.

## Rotas Disponíveis

- **POST /usuarios** - Criar um novo usuário
- **GET /usuarios/:id** - Buscar usuário por ID
- **GET /usuarios/email/:email** - Buscar usuário por email
- **GET /usuarios/nome/:nome** - Buscar usuário(s) por nome
- **DELETE /usuarios/:id** - Deletar usuário por ID
- **PUT /usuarios/:id** - Atualizar usuário por ID
- **POST /login** - Login e geração do token JWT
- **POST /logout** - Logout e invalidação do token JWT

### Exemplo de requisição
```bash
POST /usuarios
Content-Type: application/json

{
  "nome": "João Silva",
  "email": "joao@exemplo.com",
  "senha": "senha123",
  "idade": 30,
  "estado": "SP",
  "cidade": "São Paulo"
}
```
### Resposta Esperada
```bash
{
  "id": 1,
  "nome": "João Silva",
  "email": "joao@exemplo.com",
  "idade": 30,
  "estado": "SP",
  "cidade": "São Paulo"
}
```


