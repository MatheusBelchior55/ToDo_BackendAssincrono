# ToDo API — FastAPI

API REST para gerenciamento de tarefas, desenvolvida com Python e FastAPI durante meus estudos de desenvolvimento Back-end.

O projeto tem como objetivo consolidar conhecimentos em construção de APIs, programação assíncrona, persistência de dados relacionais, migrações de banco de dados e testes automatizados.

**Status:** Em desenvolvimento — projeto atualmente pausado.

## Tecnologias utilizadas

* **Python:** linguagem principal.
* **FastAPI:** framework para desenvolvimento de APIs REST.
* **SQLAlchemy:** ORM para interação com o banco de dados.
* **SQLite:** banco de dados relacional utilizado no projeto.
* **Alembic:** gerenciamento de migrações do banco de dados.
* **Pydantic:** validação e serialização de dados.
* **Poetry:** gerenciamento de dependências e ambiente virtual.
* **Pytest:** execução de testes automatizados.
* **Uvicorn:** servidor ASGI para execução da aplicação.

## Funcionalidades

* Endpoints REST para gerenciamento de tarefas.
* Processamento assíncrono utilizando `async` e `await`, conforme implementado na aplicação.
* Validação e serialização de dados.
* Persistência de dados com SQLite.
* Gerenciamento de alterações no esquema do banco com Alembic.
* Testes automatizados para verificar o comportamento da aplicação.

## Pré-requisitos

Antes de executar o projeto, é necessário ter instalado:

* Python em uma versão compatível com as dependências.
* Poetry.
* Git.

**Não é necessário instalar Docker ou PostgreSQL.** A versão atual utiliza SQLite, que armazena os dados em um arquivo local.

## Como executar o projeto

### 1. Clonar o repositório

```bash
git clone https://github.com/MatheusBelchior55/ToDo_BackendAssincrono.git
cd ToDo_BakcndAssincrono.git
```

Substitua os valores pelos dados do seu repositório.

### 2. Instalar as dependências

Na raiz do projeto, execute:

```bash
poetry install
```

O Poetry instalará as dependências declaradas no `pyproject.toml`, utilizando o arquivo `poetry.lock` para reproduzir as versões resolvidas.

### 3. Configurar o ambiente

Verifique se as variáveis de ambiente necessárias estão configuradas conforme o código da aplicação.

O repositório contém um arquivo `.env`. Por segurança, não compartilhe credenciais ou informações sensíveis desse arquivo.

Como o projeto utiliza SQLite, não é necessário iniciar um servidor de banco de dados separado.

### 4. Executar as migrações

Para aplicar as migrações pendentes do banco de dados, execute:

```bash
poetry run alembic upgrade head
```

Esse comando aplica as migrações configuradas no Alembic. A execução depende de a configuração de conexão e o ambiente estarem corretos.

### 5. Iniciar a aplicação

Caso o objeto `app` esteja definido no módulo `fastapi_zero.app`, execute:

```bash
poetry run uvicorn fastapi_zero.app:app --reload
```

O parâmetro `--reload` reinicia automaticamente o servidor durante o desenvolvimento quando alterações no código são detectadas.

Se o ponto de entrada estiver em outro módulo, ajuste o comando de acordo com a estrutura da aplicação.

### 6. Acessar a documentação da API

Após iniciar o servidor, acesse:

* **Swagger UI:** http://127.0.0.1:8000/docs
* **ReDoc:** http://127.0.0.1:8000/redoc

A documentação interativa permite consultar os endpoints disponíveis, visualizar os parâmetros e testar as requisições da API.

## Banco de dados

O projeto utiliza **SQLite**, um banco de dados relacional que armazena as informações em um arquivo local, dispensando a necessidade de executar um serviço de banco de dados separado.

O repositório contém o arquivo `database.db` e o diretório `migrations`, utilizado no gerenciamento das alterações do esquema do banco.

O Alembic permite versionar essas alterações e aplicá-las de maneira controlada ao longo do desenvolvimento.

## Programação assíncrona

A aplicação explora o modelo assíncrono do Python por meio de `async` e `await`, com suporte do FastAPI.

Esse modelo permite que operações de entrada e saída compatíveis, como acesso ao banco de dados, aguardem seus resultados sem bloquear desnecessariamente o event loop.

O uso de código assíncrono deve ser acompanhado de bibliotecas e operações compatíveis com esse modelo para que os benefícios sejam efetivos.

## Testes automatizados

O projeto possui um diretório dedicado aos testes.

Para executar os testes com Pytest, utilize:

```bash
poetry run pytest
```

O resultado depende das configurações e dos testes presentes no repositório.

## Estrutura do projeto

```text
.
├── fastapi_zero/
├── migrations/
├── tests/
├── .env
├── .gitignore
├── alembic.ini
├── database.db
├── poetry.lock
├── pyproject.toml
└── README.md
```

## Objetivos de aprendizagem

O desenvolvimento deste projeto contribui para a consolidação de conhecimentos em:

* Desenvolvimento Back-end com Python.
* Construção de APIs REST com FastAPI.
* Programação assíncrona.
* Validação e serialização de dados.
* Persistência em bancos de dados relacionais.
* Migrações de banco de dados com Alembic.
* Testes automatizados com Pytest.
* Gerenciamento de dependências com Poetry.

**Projeto de estudo:** aplicação prática de conceitos de desenvolvimento Back-end com Python, FastAPI e ferramentas do ecossistema moderno de desenvolvimento.
