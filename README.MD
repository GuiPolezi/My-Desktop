# my-desktop
# 🚀 Refine CRUD Admin (React + Auth0)

![React](https://img.shields.io/badge/React-19-blue)
![Refine](https://img.shields.io/badge/Refine-Framework-purple)
![Auth0](https://img.shields.io/badge/Auth0-Authentication-orange)
![Vite](https://img.shields.io/badge/Vite-Build_Tool-yellow)
![Tailwind](https://img.shields.io/badge/TailwindCSS-Styling-38B2AC)
![License](https://img.shields.io/badge/license-MIT-green)

Painel administrativo moderno desenvolvido com **React + Refine** para
gerenciamento de **operações CRUD** com **autenticação segura via
Auth0**.

O projeto demonstra como construir uma aplicação administrativa
escalável utilizando:

-   arquitetura baseada em **resources**
-   **rotas protegidas**
-   **formulários modernos**
-   **tabelas avançadas**
-   integração com **API REST**

------------------------------------------------------------------------

# 📸 Preview

> Sugestão: adicione screenshots aqui quando publicar no GitHub.

    /screenshots
       dashboard.png
       blogposts.png
       categories.png

------------------------------------------------------------------------

# 🧰 Stack Tecnológica

## ⚙️ Core

-   React 19
-   Refine Framework

## 🧭 Roteamento

-   React Router v7

## 🔐 Autenticação

-   Auth0
-   @auth0/auth0-react

## 📊 Tabelas

-   TanStack Table v8
-   @refinedev/react-table

## 📝 Formulários

-   React Hook Form
-   @refinedev/react-hook-form

## 🎨 Estilização

-   Tailwind CSS
-   CSS Customizado

## 🌐 Comunicação com API

-   Axios
-   @refinedev/rest

## ⚡ Build Tool

-   Vite

------------------------------------------------------------------------

# 🏗 Arquitetura do Projeto

A aplicação segue a arquitetura recomendada pelo **Refine**, baseada em
**resources** e **providers**.

    src
    │
    ├── pages
    │   ├── blog_posts
    │   │   ├── list
    │   │   └── show
    │   │
    │   └── categories
    │       ├── create
    │       └── edit
    │
    ├── components
    ├── providers
    ├── routes
    ├── styles
    └── App.tsx

------------------------------------------------------------------------

# 🔐 Autenticação (Auth0)

A autenticação é gerenciada utilizando **Auth0**.

## Provider Global

Toda aplicação é envolvida por:

    <Auth0Provider>

Configuração necessária:

-   Domain
-   Client ID
-   Redirect URI

------------------------------------------------------------------------

## Integração com Refine

O Refine utiliza um **AuthProvider** que controla:

-   login
-   logout
-   verificação de autenticação
-   controle de tokens

------------------------------------------------------------------------

## Fluxo de Login

O login ocorre através do método:

    loginWithRedirect()

Fluxo:

    User → Login Button → Auth0 → Callback → Aplicação

------------------------------------------------------------------------

# 🌐 Consumo da API

A aplicação consome uma API REST de testes.

    https://api.fake-rest.refine.dev

Configurada via variável de ambiente:

    VITE_API_URL

O Refine utiliza:

    createSimpleRestDataProvider

Isso padroniza:

-   GET
-   POST
-   PUT
-   DELETE

------------------------------------------------------------------------

# 🧭 Sistema de Rotas

O roteamento utiliza **React Router**.

    <BrowserRouter>

## Rotas protegidas

As páginas internas utilizam:

    <Authenticated>

Se o usuário não estiver autenticado:

    redirect → /login

------------------------------------------------------------------------

## Redirecionamento inicial

    / → /blog_posts

------------------------------------------------------------------------

# 📦 Recursos da Aplicação

O sistema possui dois **resources principais**:

  Resource     Descrição
  ------------ ------------------------
  blog_posts   Gerenciamento de posts
  categories   Categorias dos posts

Ambos possuem:

    canDelete: true

------------------------------------------------------------------------

# 📝 Blog Posts

## Listagem

Página responsável por exibir todos os posts.

Tecnologia utilizada:

-   TanStack Table

### Colunas

-   ID
-   Title
-   Content
-   Status
-   CreatedAt

### Recursos da tabela

✔ Paginação\
✔ Navegação entre páginas\
✔ Limite de itens por página\
✔ Ações rápidas

Botões disponíveis:

-   Show
-   Edit

------------------------------------------------------------------------

## Relação com categorias

Os posts possuem relacionamento com categorias.

Busca feita com:

    useMany()

------------------------------------------------------------------------

# 🔎 Visualização de Post

Página:

    BlogPostShow

Dados obtidos com:

    useShow()

ID da URL:

    useResourceParams()

Categoria relacionada:

    useOne()

------------------------------------------------------------------------

# 📂 Categories

Gerenciamento de categorias.

------------------------------------------------------------------------

## ➕ Criar Categoria

Formulário simples contendo:

    Title (required)

Tecnologia:

-   React Hook Form
-   useForm (Refine)

Requisição enviada:

    POST /categories

------------------------------------------------------------------------

## ✏️ Editar Categoria

Reutiliza o mesmo formulário da criação.

Requisição:

    PUT / PATCH

------------------------------------------------------------------------

# 🎨 Layout e Estilização

O projeto utiliza **Tailwind CSS** como base.

Arquivo global:

    @tailwind base;
    @tailwind components;
    @tailwind utilities;

------------------------------------------------------------------------

## CSS customizado

Foram adicionados estilos específicos para:

-   tabelas
-   botões
-   formulários
-   breadcrumbs
-   layout

------------------------------------------------------------------------

# 📱 Responsividade

O layout possui adaptação automática para telas menores.

Breakpoint principal:

    751px

------------------------------------------------------------------------

# 📋 Menu Dinâmico

O menu é gerado automaticamente utilizando:

    useMenu()

O Refine cria os links baseado nos **resources registrados**.

Exemplo:

    resources={[
     { name: "blog_posts" },
     { name: "categories" }
    ]}

------------------------------------------------------------------------

# 🚀 Como Rodar o Projeto

## 1️⃣ Clonar o repositório

    git clone https://github.com/seu-usuario/seu-repositorio.git

------------------------------------------------------------------------

## 2️⃣ Instalar dependências

    npm install

ou

    yarn install

------------------------------------------------------------------------

## 3️⃣ Criar arquivo .env

    VITE_API_URL=https://api.fake-rest.refine.dev

    VITE_AUTH0_DOMAIN=seu-dominio
    VITE_AUTH0_CLIENT_ID=seu-client-id

------------------------------------------------------------------------

## 4️⃣ Rodar o projeto

    npm run dev

------------------------------------------------------------------------

# 🧪 Possíveis Melhorias Futuras

-   Dashboard com gráficos
-   Sistema de permissões por grupo
-   Upload de imagens
-   Busca global
-   Filtros avançados
-   Dark Mode

------------------------------------------------------------------------

# 📚 Objetivo do Projeto

Este projeto demonstra como construir um **painel administrativo
completo** utilizando:

-   Refine
-   React
-   Auth0
-   REST APIs

Servindo como **base para sistemas administrativos escaláveis**.

------------------------------------------------------------------------

# 👨‍💻 Autor

Projeto desenvolvido para estudo e demonstração de arquitetura moderna
com React.

------------------------------------------------------------------------

# 📄 Licença

MIT License
