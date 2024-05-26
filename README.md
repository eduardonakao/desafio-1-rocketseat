# API de Gerenciamento de Tasks

## Sobre o Projeto

Este projeto é uma API desenvolvida para realizar o gerenciamento de tasks (tarefas), incluindo funcionalidades de CRUD e a importação em massa de tasks a partir de um arquivo CSV.

## Funcionalidades

A API possui as seguintes funcionalidades:

- **Criação de uma task**
- **Listagem de todas as tasks**
- **Atualização de uma task pelo `id`**
- **Remoção de uma task pelo `id`**
- **Marcação de uma task como completa pelo `id`**
- **Importação em massa de tasks por um arquivo CSV**

### Estrutura de uma Task

Cada task possui as seguintes propriedades:

- `id` - Identificador único da task
- `title` - Título da task
- `description` - Descrição detalhada da task
- `completed_at` - Data de conclusão da task, inicialmente `null`
- `created_at` - Data de criação da task
- `updated_at` - Data da última atualização da task

### Rotas e Regras de Negócio

#### 1. Criação de uma Task

**Rota:** `POST - /tasks`

- Cria uma nova task no banco de dados.
- Campos esperados no corpo da requisição: `title` e `description`.
- Campos preenchidos automaticamente: `id`, `created_at`, `updated_at`, e `completed_at`.

#### 2. Listagem de Todas as Tasks

**Rota:** `GET - /tasks`

- Lista todas as tasks salvas no banco de dados.
- Permite busca por `title` e `description` como parâmetros de query.

#### 3. Atualização de uma Task pelo `id`

**Rota:** `PUT - /tasks/:id`

- Atualiza uma task existente pelo `id`.
- Campos atualizáveis: `title` e/ou `description`.
- Validação: verifica se o `id` existe no banco de dados antes da atualização.

#### 4. Remoção de uma Task pelo `id`

**Rota:** `DELETE - /tasks/:id`

- Remove uma task pelo `id`.
- Validação: verifica se o `id` existe no banco de dados antes da remoção.

#### 5. Marcação de uma Task como Completa pelo `id`

**Rota:** `PATCH - /tasks/:id/complete`

- Marca uma task como completa ou incompleta.
- Validação: verifica se o `id` existe no banco de dados antes da alteração.

#### 6. Importação em Massa de Tasks por um Arquivo CSV

**Rota:** `POST - /tasks/import`

- Permite a importação de múltiplas tasks a partir de um arquivo CSV.
- O arquivo CSV deve conter colunas para `title` e `description`.

## Como Executar

1. **Clone o repositório:**
   ```bash
   git clone <URL do Repositório>
   cd <Nome do Repositório>

2. **Instale as dependências:**
    npm install

3. **Inicie a aplicação:**
    npm run dev

4. **Utilize uma API Client para fazer os testes das rotas**
    Insomnia