# Auth App Prof

Projeto desenvolvido em **Laravel 12** com autenticação, painel protegido e funcionalidades de CRUD para gerenciamento de **posts** e **categorias**.

A aplicação utiliza **Laravel Breeze**, **Blade**, **Alpine.js**, **TailwindCSS**, **Vite** e banco de dados **MySQL**.

## Sobre o projeto

Este projeto é um sistema web de blog com autenticação de usuários. Após realizar login, o usuário pode acessar uma área protegida para gerenciar categorias e posts.

O sistema possui recursos como:

- Cadastro, edição, listagem e exclusão de categorias;
- Cadastro, edição, listagem e exclusão de posts;
- Upload de imagens para os posts;
- Autenticação de usuários;
- Rotas protegidas por login;
- Interface com Blade, TailwindCSS e Alpine.js;
- Integração com banco de dados MySQL.

## Tecnologias utilizadas

- PHP 8.2+
- Laravel 12
- Laravel Breeze
- MySQL
- Blade
- Alpine.js
- TailwindCSS
- Vite
- Composer
- NPM

## Requisitos

Antes de iniciar, é necessário ter instalado em sua máquina:

- PHP 8.2 ou superior
- Composer
- Node.js
- NPM
- MySQL
- Git

## Como instalar o projeto

Clone o repositório:

```bash
git clone https://github.com/BrunoAttina/auth-app-prof.git
```

Acesse a pasta do projeto:

```bash
cd auth-app-prof
```

Instale as dependências do PHP:

```bash
composer install
```

Instale as dependências do Node.js:

```bash
npm install
```

Crie o arquivo `.env` com base no arquivo de exemplo:

```bash
cp .env.example .env
```

Gere a chave da aplicação:

```bash
php artisan key:generate
```

## Configuração do banco de dados

No arquivo `.env`, configure as informações do seu banco MySQL:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=auth_app_prof
DB_USERNAME=root
DB_PASSWORD=
```

Crie o banco de dados no MySQL com o mesmo nome definido em `DB_DATABASE`.

Depois, execute as migrations:

```bash
php artisan migrate
```

Caso o projeto tenha seeders configurados, você também pode executar:

```bash
php artisan db:seed
```

## Link simbólico para imagens

Como o projeto trabalha com upload de imagens, execute o comando abaixo para criar o link simbólico da pasta `storage`:

```bash
php artisan storage:link
```

## Como executar o projeto

Em um terminal, inicie o servidor Laravel:

```bash
php artisan serve
```

Em outro terminal, execute o Vite:

```bash
npm run dev
```

Acesse o projeto no navegador:

```text
http://127.0.0.1:8000
```

## Comando alternativo de desenvolvimento

O projeto também possui um script de desenvolvimento configurado no Composer:

```bash
composer run dev
```

Esse comando pode iniciar, ao mesmo tempo, o servidor Laravel, a fila, os logs e o Vite.

## Autenticação

O projeto utiliza Laravel Breeze para autenticação.

Funcionalidades disponíveis:

- Registro de usuário;
- Login;
- Logout;
- Recuperação de senha;
- Edição de perfil;
- Área protegida por autenticação.

## Rotas principais

As principais áreas do sistema são protegidas por autenticação.

Exemplos de rotas:

```text
/dashboard
/profile
/categorias
/posts
```

As rotas de categorias e posts utilizam `Route::resource`, permitindo operações completas de CRUD.

## Estrutura básica do projeto

```text
app/
├── Http/
│   └── Controllers/
├── Models/

database/
├── migrations/
├── seeders/

resources/
├── views/
├── css/
├── js/

routes/
├── web.php
├── auth.php

public/
storage/
```

## Funcionalidades

### Categorias

Permite gerenciar as categorias utilizadas nos posts.

Operações disponíveis:

- Listar categorias;
- Criar categoria;
- Editar categoria;
- Excluir categoria;
- Visualizar detalhes.

### Posts

Permite gerenciar os posts do blog.

Operações disponíveis:

- Listar posts;
- Criar post;
- Editar post;
- Excluir post;
- Visualizar detalhes;
- Enviar imagem para o post;
- Associar post a uma categoria.

## Compilar assets para produção

Para gerar os arquivos finais de CSS e JavaScript, execute:

```bash
npm run build
```

## Executar testes

Para executar os testes do projeto:

```bash
php artisan test
```

Ou pelo Composer:

```bash
composer test
```

## Possíveis problemas

### Erro ao carregar imagens

Execute:

```bash
php artisan storage:link
```

### Erro de conexão com o banco

Verifique se:

- O MySQL está em execução;
- O banco de dados foi criado;
- As configurações do `.env` estão corretas;
- As migrations foram executadas.

### Alterações no CSS ou JS não aparecem

Execute novamente:

```bash
npm run dev
```

ou gere os arquivos de produção:

```bash
npm run build
```

## Autor

Desenvolvido por **Bruno Attina**.

GitHub: [@BrunoAttina](https://github.com/BrunoAttina)

## Licença

Este projeto utiliza a licença MIT.
