# Django Template by Hamasakis

Este repositório contém um template robusto e configurado para iniciar novos projetos Django rapidamente. Desenvolvido por Hamasakis, este boilerplate integra as melhores práticas e ferramentas essenciais para aplicações modernas, focando em escalabilidade e facilidade de desenvolvimento.

## 🚀 Funcionalidades e Tecnologias

Este template vem pré-configurado com uma stack poderosa:

- **Backend Framework**: [Django](https://www.djangoproject.com/) (v5.2+) - O framework web para perfeccionistas com prazos.
- **REST API**: [Django REST Framework](https://www.django-rest-framework.org/) - Toolkit poderoso e flexível para construir Web APIs.
- **Task Queue & Async**: [Celery](https://docs.celeryq.dev/) - Fila de tarefas distribuída assíncrona.
- **Scheduling**: [Django Celery Beat](https://django-celery-beat.readthedocs.io/) - Agendamento de tarefas periódicas.
- **Database**: [PostgreSQL](https://www.postgresql.org/) - Banco de dados relacional open source avançado.
- **Caching & Broker**: [Redis](https://redis.io/) - Armazenamento de estrutura de dados em memória, usado como banco de dados, cache e message broker.
- **Admin Interface**: [Django Jazzmin](https://github.com/farridav/django-jazzmin) - Tema administrativo moderno e customizável para o Django Admin.
- **Containerization**: [Docker](https://www.docker.com/) & Docker Compose - Ambiente de desenvolvimento isolado e replicável.

## 📋 Pré-requisitos

Certifique-se de ter instalado em sua máquina:

- [Python 3.10+](https://www.python.org/)
- [Docker](https://docs.docker.com/get-docker/) & Docker Compose
- [Git](https://git-scm.com/)

## 🛠️ Instalação e Configuração

Siga os passos abaixo para levantar o ambiente de desenvolvimento:

### 1. Clone o repositório

```bash
git clone <https://github.com/gabehamasaki/django-template>
cd <nome-do-diretorio>
```

### 2. Configure o Ambiente Virtual

É recomendado usar um ambiente virtual para isolar as dependências do projeto.

```bash
python -m venv venv
# No Linux/Mac:
source venv/bin/activate
# No Windows:
.\venv\Scripts\activate
```

### 3. Instale as Dependências

```bash
pip install -r requirements.txt
```

### 4. Inicialize os Serviços (Docker)

Utilize o Docker Compose para subir os serviços de infraestrutura (PostgreSQL, Redis, etc.).

```bash
docker-compose up -d
```

### 5. Aplique as Migrations

Configure o banco de dados inicial:

```bash
python manage.py migrate
```

### 6. Crie um Superusuário

Para acessar o painel administrativo:

```bash
python manage.py createsuperuser
```

## ▶️ Executando o Projeto

### Servidor de Desenvolvimento

Para rodar a aplicação Django:

```bash
python manage.py runserver
```

Acesse em: `http://localhost:8000`

### Celery Worker

Para processar tarefas em background:

```bash
celery -A core worker -l info
```

### Celery Beat

Para agendamento de tarefas periódicas:

```bash
celery -A core beat -l info
```

## 📂 Estrutura do Projeto

```plaintext
.
├── core/                # Configurações principais do projeto (settings, urls, celery, wsgi/asgi)
├── docker-compose.yml   # Orquestração dos containers (Postgres, etc.)
├── manage.py            # Utilitário de linha de comando do Django
├── requiriments.txt     # Dependências do projeto Python
└── readme.md            # Documentação do projeto
```

## ⚙️ Configurações Importantes

- **Settings**: As configurações principais estão em `core/settings.py`.
- **Database**: Configurado para conectar ao PostgreSQL rodando no Docker.
- **Celery**: Configurado em `core/celery.py` com Redis como broker.
- **Jazzmin**: A interface admin já vem com o tema Jazzmin aplicado.

## 🤝 Contribuição

Sinta-se à vontade para fazer um fork deste template e adaptá-lo às suas necessidades. Pull requests são bem-vindos.

---
Desenvolvido por **Hamasakis**.
