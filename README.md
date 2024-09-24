# Projeto Docker com PHP, MySQL, phpMyAdmin e React

Este projeto utiliza Docker para criar um ambiente de desenvolvimento integrado com **PHP**, **MySQL**, **phpMyAdmin** e **React**.

## Pré-requisitos

Antes de iniciar, certifique-se de ter os seguintes softwares instalados na sua máquina:

- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Estrutura do Projeto

A estrutura de diretórios é a seguinte:

```
docker-php-mysql-react
│
├── backend
│   ├── Dockerfile
│   └── src/
│       └── index.php
├── frontend
│   ├── Dockerfile
│   └── src/
│       └── App.js
└── docker-compose.yml
```

- **backend**: Diretório com o código PHP e configuração do Docker para rodar o Apache com PHP.
- **frontend**: Diretório com o código React e configuração do Docker para rodar o servidor React.
- **docker-compose.yml**: Arquivo de configuração do Docker Compose para orquestrar os containers.

## Instruções de Inicialização

Siga os passos abaixo para rodar o projeto em uma nova máquina:

### 1. Clone o Repositório

Clone este repositório para a sua máquina:

```bash
git clone <[url-do-repositorio](https://github.com/correairwing/teste)>
cd teste
```

### 2. Build e Inicialização do Projeto

Use o comando abaixo para construir e iniciar todos os serviços:

```bash
docker-compose up --build
```

O Docker Compose vai baixar todas as imagens necessárias (PHP, MySQL, phpMyAdmin, Node.js) e criar os containers correspondentes.

### 3. Acessando os Serviços

Após rodar o comando anterior, você pode acessar os seguintes serviços:

- **Aplicação PHP**: [http://localhost:8000](http://localhost:8000)
- **phpMyAdmin**: [http://localhost:8080](http://localhost:8080)
- **Aplicação React**: [http://localhost:3000](http://localhost:3000)

### 4. Credenciais do phpMyAdmin

Para acessar o phpMyAdmin, use as seguintes credenciais:

- **Usuário**: `root`
- **Senha**: `rootpassword`

### 5. Alterar a Porta do MySQL (opcional)

Caso a porta `3306` já esteja em uso, você pode modificar a porta local no arquivo `docker-compose.yml`. Alterando:

```yaml
mysql:
  ports:
    - "3307:3306"  # Altere a porta local de 3306 para 3307
```

Depois, rode novamente o comando:

```bash
docker-compose up --build
```

## Parando os Containers

Para parar todos os containers, use:

```bash
docker-compose down
```

## Debugging

- Se você encontrar problemas de conectividade com o MySQL, verifique as portas e certifique-se de que o serviço está rodando corretamente.
- Use `docker ps` para listar os containers em execução e `docker logs <container_name>` para verificar os logs de um container específico.

## Tecnologias Utilizadas

- **PHP** 7.4 com Apache
- **MySQL** 5.7
- **phpMyAdmin** para gerenciamento de banco de dados
- **React** para o frontend
