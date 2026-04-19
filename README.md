# 💰 Controle Financeiro Pessoal / Personal Finance Tracker

> 🇧🇷 Português abaixo · 🇬🇧 English below

---

## 🇧🇷 Português (Brasil)

### Sobre o Projeto

Um aplicativo web de **página única (SPA)** para controle de finanças pessoais, criado especificamente para quem tem uma renda **não convencional** — como trabalhadores autônomos, freelancers, criadores de conteúdo, prestadores de serviço por plataforma, ou qualquer pessoa cujos ganhos variam semana a semana e vêm de múltiplas fontes.

Desenvolvido com o auxílio do **Google AI Studio**, o app roda diretamente no navegador e usa o **Firebase** como backend para autenticação e armazenamento de dados em tempo real.

---

### ✨ Funcionalidades

#### 🔐 Autenticação
- Login e cadastro via e-mail e senha (Firebase Auth)
- Detecção automática de moeda com base no fuso horário do usuário no momento do cadastro
- Suporte a **GBP (£)**, **BRL (R$)**, **EUR (€)** e **USD ($)**

#### 📊 Dashboard Semanal
- Visão geral da **semana atual** com navegação entre semanas anteriores
- Resumo de: ganhos brutos, ganhos líquidos, gastos variáveis, gastos fixos, saldo final e meta semanal
- **Indicador de progresso** visual em relação à meta da semana
- Gráfico de barras com os ganhos por dia da semana (clicável para ver detalhes de cada dia)

#### 💸 Gerenciamento de Ganhos
- Registro de entradas com data, valor, fonte de renda e status de recebimento (recebido / pendente)
- **Cálculo automático do valor líquido** com base na taxa da plataforma (percentual ou valor fixo)
- Edição e exclusão de entradas
- Marcação individual ou em lote como "recebido" (por semana, semanas anteriores ou todas)

#### 🧾 Gastos Variáveis
- Registro de gastos pontuais vinculados a uma semana específica
- Edição e exclusão

#### 📌 Gastos Fixos
- Cadastro de despesas fixas organizadas por **categorias** (ex: Moradia, Transporte, Saúde...)
- Marcação semanal de itens como **pagos/pendentes**, com status visual
- Possibilidade de **sobrescrever o valor** de um item fixo para uma semana específica (ex: conta de luz variou)
- **Snapshot automático**: ao marcar um item como pago, o sistema "congela" os valores daquela semana para que alterações futuras nas configurações não afetem o histórico
- **Ajuste semanal manual**: caso os gastos fixos de uma semana sejam completamente diferentes do padrão, é possível inserir um total manual e uma nota explicativa com suporte a formatação básica (negrito, itálico, sublinhado)

#### 🏦 Fontes de Renda (Plataformas)
- Cadastro de múltiplas fontes de renda com nome e tipo de taxa:
  - **Sem taxa** (valor bruto = líquido)
  - **Taxa percentual** (ex: plataforma retém 20%)
  - **Taxa fixa** (ex: plataforma desconta £5 por transação)
- O valor líquido é calculado automaticamente em todos os registros

#### 📅 Visão Mensal
- Resumo financeiro por mês com navegação entre meses
- Gráfico de barras com ganhos líquidos por dia da semana no mês selecionado
- Totais de ganhos, gastos e saldo do mês

#### ⚙️ Configurações
- Alteração de moeda
- Definição da meta semanal de ganhos
- Acesso ao gerenciador de fontes de renda
- **Limpar todos os dados** (com confirmação dupla)

#### 🎓 Tutorial Interativo
- Exibido automaticamente para novos usuários
- Guia por todas as funcionalidades principais do app

---

### 🛠️ Tecnologias Utilizadas

| Tecnologia | Uso |
|---|---|
| HTML5 + JavaScript (Vanilla) | Estrutura e lógica da aplicação |
| [Tailwind CSS](https://tailwindcss.com/) (CDN) | Estilização e layout responsivo |
| [Firebase Auth](https://firebase.google.com/docs/auth) | Autenticação de usuários |
| [Firebase Firestore](https://firebase.google.com/docs/firestore) | Banco de dados em tempo real |
| Google AI Studio | Assistência no desenvolvimento |

---

### 🚀 Como Usar

O app é um **único arquivo HTML** (`index.html`). Não há instalação, build ou dependências locais.

1. **Clone ou baixe** este repositório
2. Abra o arquivo `index.html` diretamente no navegador **ou** hospede-o em qualquer serviço de hosting estático (GitHub Pages, Netlify, Vercel, etc.)
3. **Crie uma conta** com e-mail e senha
4. Comece a registrar seus ganhos e gastos!

> ⚠️ **Importante:** O app usa um projeto Firebase próprio do autor. Para uso pessoal em produção, é recomendado criar seu próprio projeto Firebase e substituir o objeto `firebaseConfig` no início do arquivo.

---

### 📁 Estrutura do Firestore

Os dados de cada usuário são armazenados sob o caminho `users/{uid}/`:

```
users/
  {uid}/
    earnings/         → Registros de ganhos
    expenses/         → Gastos variáveis
    weeklyFixedExpenses/ → Estado semanal dos gastos fixos
    settings/
      preferences     → Moeda, plataformas, status do tutorial
      fixedExpenses   → Categorias e itens de gastos fixos
      weekGoal        → Meta semanal
```

---

### 💡 Motivação

Os principais aplicativos de finanças pessoais do mercado são pensados para quem recebe um salário fixo mensal. Para quem trabalha de forma não convencional — com ganhos semanais variáveis, múltiplas plataformas e taxas diferentes —, esses apps não funcionam bem. Este projeto nasceu da necessidade real de ter uma ferramenta adaptada a esse tipo de renda.

---

---

## 🇬🇧 English

### About the Project

A **single-page web application (SPA)** for personal finance tracking, built specifically for people with **non-conventional income** — such as freelancers, gig workers, content creators, platform-based service providers, or anyone whose earnings vary week to week and come from multiple sources.

Developed with the assistance of **Google AI Studio**, the app runs directly in the browser and uses **Firebase** as its backend for authentication and real-time data storage.

---

### ✨ Features

#### 🔐 Authentication
- Login and sign-up via email and password (Firebase Auth)
- Automatic currency detection based on the user's timezone at sign-up
- Supports **GBP (£)**, **BRL (R$)**, **EUR (€)**, and **USD ($)**

#### 📊 Weekly Dashboard
- Overview of the **current week** with navigation to past weeks
- Summary of: gross earnings, net earnings, variable expenses, fixed expenses, final balance, and weekly goal
- Visual **progress indicator** toward the week's goal
- Bar chart of earnings per day of the week (clickable to view each day's details)

#### 💸 Earnings Management
- Log income entries with date, amount, income source, and payment status (received / pending)
- **Automatic net value calculation** based on the platform's fee (percentage or fixed amount)
- Edit and delete entries
- Mark individual or bulk entries as "received" (for the current week, previous weeks, or all)

#### 🧾 Variable Expenses
- Log one-off expenses linked to a specific week
- Edit and delete

#### 📌 Fixed Expenses
- Register recurring expenses organized by **categories** (e.g. Housing, Transport, Health...)
- Weekly marking of items as **paid/pending** with visual status
- Ability to **override the value** of a fixed item for a specific week (e.g. an unusually high utility bill)
- **Automatic snapshot**: when an item is marked as paid, the system "freezes" that week's values so future changes to settings don't affect historical records
- **Manual weekly override**: if a week's fixed costs are completely different from the default, you can enter a custom total and add a formatted note (bold, italic, underline supported)

#### 🏦 Income Sources (Platforms)
- Register multiple income sources with a name and fee type:
  - **No fee** (gross = net)
  - **Percentage fee** (e.g. platform keeps 20%)
  - **Fixed fee** (e.g. platform deducts £5 per transaction)
- Net value is automatically calculated across all records

#### 📅 Monthly View
- Financial summary by month with month-to-month navigation
- Bar chart of net earnings by day of the week for the selected month
- Monthly totals for earnings, expenses, and balance

#### ⚙️ Settings
- Change currency
- Set weekly earnings goal
- Access the income sources manager
- **Clear all data** (with double confirmation)

#### 🎓 Interactive Tutorial
- Automatically shown to new users
- Guides through all the main features of the app

---

### 🛠️ Technologies Used

| Technology | Usage |
|---|---|
| HTML5 + JavaScript (Vanilla) | App structure and logic |
| [Tailwind CSS](https://tailwindcss.com/) (CDN) | Styling and responsive layout |
| [Firebase Auth](https://firebase.google.com/docs/auth) | User authentication |
| [Firebase Firestore](https://firebase.google.com/docs/firestore) | Real-time database |
| Google AI Studio | Development assistance |

---

### 🚀 How to Use

The app is a **single HTML file** (`index.html`). There is no installation, build step, or local dependencies.

1. **Clone or download** this repository
2. Open `index.html` directly in a browser **or** host it on any static hosting service (GitHub Pages, Netlify, Vercel, etc.)
3. **Create an account** with your email and password
4. Start logging your earnings and expenses!

> ⚠️ **Important:** The app uses the author's own Firebase project. For personal production use, it is recommended to create your own Firebase project and replace the `firebaseConfig` object at the top of the file with your own credentials.

---

### 📁 Firestore Data Structure

Each user's data is stored under the path `users/{uid}/`:

```
users/
  {uid}/
    earnings/              → Income entries
    expenses/              → Variable expenses
    weeklyFixedExpenses/   → Weekly state of fixed expenses
    settings/
      preferences          → Currency, platforms, tutorial status
      fixedExpenses        → Fixed expense categories and items
      weekGoal             → Weekly earnings goal
```

---

### 💡 Motivation

Most personal finance apps on the market are designed for people who receive a fixed monthly salary. For those who work unconventionally — with variable weekly earnings, multiple platforms, and different fee structures — those apps simply don't cut it. This project was born out of a real need for a tool adapted to that kind of income.
