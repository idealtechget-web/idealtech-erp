#IDEAL ERP MEI PRO — by Zenilson Araújo de Sousa Lacerda

> Sistema de Gestão Completo para Microempreendedor Individual (MEI)

![Version](https://img.shields.io/badge/versão-7.2.1--fix-blue)
![Platform](https://img.shields.io/badge/plataforma-SaaS%20%7C%20Web-green)
![License](https://img.shields.io/badge/licença-Proprietária-red)

---

## 🌐 Acesso

**URL de Produção:** [https://erp.idealtech.srv.br](https://erp.idealtech.srv.br)

---

## 📋 Sobre o Projeto

O **IDEAL ERP MEI PRO** é um sistema de gestão completo desenvolvido para MEIs brasileiros. Roda 100% no navegador, sem instalação, com dados na nuvem via Supabase.

### Funcionalidades

- 🛠️ **Ordens de Serviço** — Manutenção, Dev/TI, Administrativo, Elétrica, Outros
- 📋 **Orçamentos** — Com conversão direta para OS
- 🛒 **PDV** — Ponto de Venda com controle de estoque
- 📦 **Estoque** — Importação XML NF-e/NFS-e, controle fiscal (NCM, CFOP, Origem)
- 💰 **Financeiro** — Receitas, despesas, categorias, recorrentes, importação OFX
- 📅 **Fluxo de Caixa** — Projeção dos próximos 30 dias
- 📑 **DRE** — Demonstrativo de Resultado com categorias
- 📈 **Relatórios** — Gerencial completo com exportação Excel e PDF
- 👥 **Clientes** — Cadastro PF/PJ com histórico
- 🧾 **Fiscal** — Relação Fiscal para emissão de NF-e/NFS-e
- 🏦 **Contas Bancárias** — Múltiplas contas com saldo e importação OFX
- 📊 **Dashboard** — KPIs, gráficos, alertas de limite MEI (R$ 81.000)

---

## 🏗️ Arquitetura

```
Frontend (HTML único)       Backend (Serverless)
─────────────────────       ────────────────────
GitHub Pages           ←→   Supabase (PostgreSQL)
erp.idealtech.srv.br        Auth + Database + RLS
```

| Camada | Tecnologia | Custo |
|--------|-----------|-------|
| Hospedagem | GitHub Pages | Gratuito |
| Banco de Dados | Supabase (500MB) | Gratuito |
| Autenticação | Supabase Auth | Gratuito |
| Domínio | Registro.br | Anual |

---

## 🚀 Deploy

Deploy automático via GitHub Pages. Qualquer commit na branch `main` atualiza em 1–3 minutos.

---

## 🗄️ Banco de Dados

**Projeto Supabase:** `lcycmvcadunkzsdmwsvk.supabase.co`

### Tabelas

| Tabela | Descrição |
|--------|-----------|
| `perfis` | Configurações da empresa |
| `os` | Ordens de Serviço |
| `orcamentos` | Orçamentos |
| `clientes` | Cadastro de clientes |
| `produtos` | Estoque |
| `servicos` | Catálogo de serviços |
| `receitas` | Lançamentos de receita |
| `despesas` | Lançamentos de despesa |
| `contas` | Contas bancárias |
| `categorias` | Categorias financeiras |
| `ofx_fitids` | Controle importação OFX |

> RLS ativo — cada usuário acessa apenas os próprios dados.

---

## 📁 Estrutura

```
idealtech-erp/
├── index.html    # Aplicação completa (single-file app)
├── CNAME         # Domínio customizado
└── README.md
```

---

## 👨‍💻 Desenvolvido por

**IdealTech** — Gestão e Tecnologia  
🌐 [idealtech.srv.br](https://idealtech.srv.br) · 📧 idealtech.get@gmail.com

*© 2026 IdealTech — Todos os direitos reservados*
