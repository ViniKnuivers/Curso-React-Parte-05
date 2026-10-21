<h1 align="center">pizza.shop · Painel do parceiro</h1>

<p align="center">
  <a href="#-português">Português</a> ·
  <a href="#-english">English</a>
</p>

<p align="center">
  <img alt="React" src="https://img.shields.io/badge/React-18-61DAFB?logo=react&logoColor=white">
  <img alt="TypeScript" src="https://img.shields.io/badge/TypeScript-5-3178C6?logo=typescript&logoColor=white">
  <img alt="Vite" src="https://img.shields.io/badge/Vite-5-646CFF?logo=vite&logoColor=white">
  <img alt="TanStack Query" src="https://img.shields.io/badge/TanStack_Query-5-FF4154?logo=reactquery&logoColor=white">
  <img alt="Tailwind CSS" src="https://img.shields.io/badge/Tailwind_CSS-3-06B6D4?logo=tailwindcss&logoColor=white">
  <img alt="Vitest" src="https://img.shields.io/badge/Vitest-1-6E9F18?logo=vitest&logoColor=white">
  <img alt="Playwright" src="https://img.shields.io/badge/Playwright-E2E-2EAD33?logo=playwright&logoColor=white">
</p>

<p align="center">
  <img alt="Dashboard do pizza.shop" src="docs/screenshots/dashboard.png" width="900">
</p>

---

## 🇧🇷 Português

### Sobre

O **pizza.shop** é o painel web de um restaurante parceiro de uma plataforma de delivery. O dono do restaurante acompanha o faturamento, vê os produtos mais vendidos e gerencia os pedidos do dia: aprova, despacha, entrega ou cancela.

Projeto desenvolvido durante a trilha de React do **Ignite, da Rocketseat**, com foco em consumo de API, cache de dados, formulários validados, interface acessível e testes automatizados.

### Funcionalidades

- **Autenticação por link mágico**: login só com e-mail e sessão por cookie
- **Cadastro de restaurante** com validação de formulário
- **Dashboard** com receita do mês, pedidos do dia e do mês, cancelamentos, gráfico de receita por período e gráfico de produtos populares
- **Gestão de pedidos** com filtros (ID, cliente e status), paginação e filtros guardados na URL
- **Detalhes do pedido** em modal, carregados só quando o modal abre
- **Fluxo de status**: pendente → em preparo → em entrega → entregue, com cancelamento enquanto pendente ou em preparo
- **Edição do perfil da loja** com atualização otimista (a interface muda antes da resposta da API e volta atrás em caso de erro)
- **Tema claro e escuro** salvo no navegador
- **Skeletons e estados de carregamento** em todas as telas
- **API simulada com MSW**, para rodar o projeto sem o back-end

### Telas

| Dashboard (escuro) | Dashboard (claro) |
| --- | --- |
| <img src="docs/screenshots/dashboard.png" alt="Dashboard escuro"> | <img src="docs/screenshots/dashboard-light.png" alt="Dashboard claro"> |

| Pedidos | Detalhes do pedido |
| --- | --- |
| <img src="docs/screenshots/orders.png" alt="Lista de pedidos"> | <img src="docs/screenshots/order-details.png" alt="Detalhes do pedido"> |

| Login | Perfil da loja |
| --- | --- |
| <img src="docs/screenshots/sign-in.png" alt="Login"> | <img src="docs/screenshots/store-profile.png" alt="Perfil da loja"> |

### Tecnologias

| Área | Ferramentas |
| --- | --- |
| Base | React 18, TypeScript, Vite |
| Rotas | React Router DOM 6 |
| Dados | TanStack React Query 5, Axios |
| Formulários | React Hook Form, Zod |
| Interface | Tailwind CSS, shadcn/ui, Radix UI, Lucide, Sonner |
| Gráficos e datas | Recharts, date-fns, React Day Picker |
| Testes | Vitest, Testing Library, Happy DOM, MSW, Playwright |
| Qualidade | ESLint (config da Rocketseat), Prettier |

### Como rodar

**Pré-requisitos:** Node.js 18 ou mais recente e pnpm.

```bash
# clone o repositório
git clone https://github.com/ViniKnuivers/<nome-do-repositorio>.git
cd <nome-do-repositorio>

# instale as dependências
pnpm install

# crie o arquivo de variáveis de ambiente
cp .env.example .env.local
```

Você pode rodar de dois jeitos:

```bash
# 1. com a API real (back-end do curso rodando em http://localhost:3333)
pnpm dev

# 2. sem back-end, com dados simulados pelo MSW (http://localhost:50789)
pnpm dev:test
```

No modo simulado, use o e-mail `johndoe@example.com` para o login funcionar.

### Variáveis de ambiente

| Variável | Descrição | Exemplo |
| --- | --- | --- |
| `VITE_API_URL` | Endereço da API | `http://localhost:3333` |
| `VITE_ENABLE_API_DELAY` | Atraso aleatório nas requisições, para ver os estados de carregamento | `true` |

### Testes

```bash
pnpm test                    # testes unitários e de componentes (Vitest)
pnpm exec playwright test    # testes ponta a ponta (Playwright)
pnpm exec playwright test --ui   # Playwright com interface visual
```

São **12 testes unitários** e **16 testes ponta a ponta**, cobrindo login, cadastro, dashboard, pedidos (listagem, paginação e filtros) e edição do perfil.

### Estrutura

```text
src/
├── api/            # uma função por endpoint
│   └── mocks/      # respostas simuladas com MSW
├── components/
│   ├── ui/         # componentes do shadcn/ui
│   └── theme/      # tema claro/escuro
├── lib/            # axios, react-query, utilitários
├── pages/
│   ├── _layouts/   # layout logado e layout de autenticação
│   ├── auth/       # login e cadastro
│   └── app/        # dashboard e pedidos
├── env.ts          # variáveis de ambiente validadas com Zod
└── routes.tsx      # rotas da aplicação
test/               # testes E2E com Playwright
```

### O que aprendi

- Separar o acesso à API em funções tipadas e deixar o **React Query** cuidar de cache, carregamento e erro
- Atualizar o cache depois de uma mutation e fazer **atualização otimista** com rollback
- Guardar filtros e paginação na **URL** com `useSearchParams`
- Validar formulários e variáveis de ambiente com **Zod**
- Montar uma interface **acessível** com Radix UI e shadcn/ui
- Testar componentes com Testing Library e fluxos completos com Playwright, usando o **MSW** no lugar da API

---

## 🇺🇸 English

### About

**pizza.shop** is the web dashboard for a restaurant partner of a food delivery platform. The restaurant owner tracks revenue, sees the best-selling products and manages the day's orders: approve, dispatch, deliver or cancel.

Built during the React track of **Rocketseat's Ignite** program, focusing on API consumption, data caching, validated forms, accessible UI and automated testing.

### Features

- **Magic link authentication**: email-only sign-in with a cookie-based session
- **Restaurant sign-up** with form validation
- **Dashboard** with monthly revenue, daily and monthly orders, cancellations, a revenue-by-period chart and a popular products chart
- **Order management** with filters (ID, customer and status), pagination and filters kept in the URL
- **Order details** in a modal, fetched only when the modal opens
- **Status flow**: pending → processing → delivering → delivered, with cancellation allowed while pending or processing
- **Store profile editing** with optimistic updates (the UI changes before the API responds and rolls back on error)
- **Light and dark theme** saved in the browser
- **Skeletons and loading states** on every screen
- **Mocked API with MSW**, so the project runs without the back-end

### Screens

| Dashboard (dark) | Dashboard (light) |
| --- | --- |
| <img src="docs/screenshots/dashboard.png" alt="Dark dashboard"> | <img src="docs/screenshots/dashboard-light.png" alt="Light dashboard"> |

| Orders | Order details |
| --- | --- |
| <img src="docs/screenshots/orders.png" alt="Orders list"> | <img src="docs/screenshots/order-details.png" alt="Order details"> |

| Sign in | Store profile |
| --- | --- |
| <img src="docs/screenshots/sign-in.png" alt="Sign in"> | <img src="docs/screenshots/store-profile.png" alt="Store profile"> |

### Tech stack

| Area | Tools |
| --- | --- |
| Core | React 18, TypeScript, Vite |
| Routing | React Router DOM 6 |
| Data | TanStack React Query 5, Axios |
| Forms | React Hook Form, Zod |
| UI | Tailwind CSS, shadcn/ui, Radix UI, Lucide, Sonner |
| Charts and dates | Recharts, date-fns, React Day Picker |
| Testing | Vitest, Testing Library, Happy DOM, MSW, Playwright |
| Code quality | ESLint (Rocketseat config), Prettier |

### Getting started

**Requirements:** Node.js 18 or newer and pnpm.

```bash
# clone the repository
git clone https://github.com/ViniKnuivers/<repository-name>.git
cd <repository-name>

# install dependencies
pnpm install

# create the environment file
cp .env.example .env.local
```

There are two ways to run it:

```bash
# 1. with the real API (course back-end running on http://localhost:3333)
pnpm dev

# 2. without a back-end, using MSW mocked data (http://localhost:50789)
pnpm dev:test
```

In mocked mode, sign in with `johndoe@example.com`.

### Environment variables

| Variable | Description | Example |
| --- | --- | --- |
| `VITE_API_URL` | API base URL | `http://localhost:3333` |
| `VITE_ENABLE_API_DELAY` | Random request delay, to see the loading states | `true` |

### Tests

```bash
pnpm test                    # unit and component tests (Vitest)
pnpm exec playwright test    # end-to-end tests (Playwright)
pnpm exec playwright test --ui   # Playwright with the visual UI
```

There are **12 unit tests** and **16 end-to-end tests**, covering sign-in, sign-up, dashboard, orders (listing, pagination and filters) and profile editing.

### Project structure

```text
src/
├── api/            # one function per endpoint
│   └── mocks/      # MSW mocked responses
├── components/
│   ├── ui/         # shadcn/ui components
│   └── theme/      # light/dark theme
├── lib/            # axios, react-query, utilities
├── pages/
│   ├── _layouts/   # signed-in layout and auth layout
│   ├── auth/       # sign-in and sign-up
│   └── app/        # dashboard and orders
├── env.ts          # environment variables validated with Zod
└── routes.tsx      # app routes
test/               # Playwright E2E tests
```

### What I learned

- Keeping API access in typed functions and letting **React Query** handle caching, loading and errors
- Updating the cache after a mutation and doing **optimistic updates** with rollback
- Keeping filters and pagination in the **URL** with `useSearchParams`
- Validating forms and environment variables with **Zod**
- Building an **accessible** UI with Radix UI and shadcn/ui
- Testing components with Testing Library and full flows with Playwright, using **MSW** instead of the real API

---

<p align="center">
  Feito por / Made by <a href="https://github.com/ViniKnuivers">Vinicius Knuivers</a>
</p>
