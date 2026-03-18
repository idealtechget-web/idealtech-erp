<div align="center">

# ⚡ IDEAL ERP MEI PRO

**Sistema de Gestão Completo para Microempreendedor Individual**

[![Versão](https://img.shields.io/badge/versão-SaaS%20Latest-blue?style=flat-square)](https://erp.idealtech.srv.br)
[![Plataforma](https://img.shields.io/badge/plataforma-Web%20%7C%20Mobile-green?style=flat-square)](https://erp.idealtech.srv.br)
[![Hospedagem](https://img.shields.io/badge/hospedagem-GitHub%20Pages-black?style=flat-square)](https://pages.github.com)
[![Banco](https://img.shields.io/badge/banco-Supabase-3ECF8E?style=flat-square)](https://supabase.com)

**🌐 [erp.idealtech.srv.br](https://erp.idealtech.srv.br)**

*by Zenilson Araújo de Sousa Lacerda — IdealTech*

</div>

---

## 📋 Sobre

O **IDEAL ERP MEI PRO** é um sistema de gestão completo desenvolvido especificamente para MEIs brasileiros. Roda 100% no navegador, sem instalação, com dados armazenados na nuvem via Supabase.

---

## ✨ Funcionalidades

| Módulo | Descrição |
|--------|-----------|
| 🛠️ **Ordens de Serviço** | Manutenção, Dev/TI, Administrativo, Elétrica, Outros. Fotos, laudos, link do cliente |
| 📋 **Orçamentos** | Criação e conversão direta para OS com um clique |
| 🛒 **PDV** | Ponto de Venda com controle de estoque e cupom térmico |
| 📦 **Estoque** | Importação via XML NF-e/NFS-e, controle fiscal completo (NCM, CFOP, Origem) |
| 💰 **Financeiro** | Receitas, despesas, categorias, recorrentes, importação OFX |
| 📅 **Fluxo de Caixa** | Projeção dos próximos 30 dias |
| 📑 **DRE** | Demonstrativo de Resultado com categorias por mês/ano |
| 📈 **Relatórios** | Gerencial completo com exportação Excel e PDF |
| 👥 **Clientes** | Cadastro PF/PJ com busca automática na Receita Federal |
| 🧾 **Relação Fiscal** | Exporta dados para emissão de NF-e/NFS-e nos emissores gratuitos |
| 🏦 **Contas Bancárias** | Múltiplas contas com saldo e importação OFX |
| 📊 **Dashboard** | KPIs, gráficos, alertas de limite MEI (R$ 81.000) |

---

## 🏗️ Arquitetura

```
┌─────────────────────────┐         ┌──────────────────────────┐
│   Frontend (Single File) │         │   Backend (Serverless)   │
│                         │         │                          │
│   GitHub Pages          │  ←───►  │   Supabase               │
│   erp.idealtech.srv.br  │         │   PostgreSQL + Auth + RLS │
└─────────────────────────┘         └──────────────────────────┘
```

| Camada | Tecnologia | Custo |
|--------|-----------|-------|
| Hospedagem | GitHub Pages | Gratuito |
| Banco de Dados | Supabase (500MB) | Gratuito |
| Autenticação | Supabase Auth | Gratuito |
| Domínio | Registro.br | Anual |

---

## 🗄️ Banco de Dados

**Projeto:** `lcycmvcadunkzsdmwsvk.supabase.co`

| Tabela | Descrição |
|--------|-----------|
| `perfis` | Configurações da empresa por usuário |
| `os` | Ordens de Serviço |
| `orcamentos` | Orçamentos |
| `clientes` | Cadastro de clientes |
| `produtos` | Estoque |
| `servicos` | Catálogo de serviços |
| `receitas` | Lançamentos de receita |
| `despesas` | Lançamentos de despesa |
| `contas` | Contas bancárias |
| `categorias` | Categorias financeiras |
| `ofx_fitids` | Controle de importação OFX |

> **RLS ativo** — cada usuário acessa apenas os próprios dados.

### Migrations necessárias

```sql
-- Colunas extras na tabela OS
ALTER TABLE public.os
  ADD COLUMN IF NOT EXISTS c_trib_nac       text DEFAULT '',
  ADD COLUMN IF NOT EXISTS c_nbs            text DEFAULT '',
  ADD COLUMN IF NOT EXISTS aparelho         text DEFAULT '',
  ADD COLUMN IF NOT EXISTS serie            text DEFAULT '',
  ADD COLUMN IF NOT EXISTS defeito          text DEFAULT '',
  ADD COLUMN IF NOT EXISTS cliente_telefone text DEFAULT '',
  ADD COLUMN IF NOT EXISTS cliente_email    text DEFAULT '',
  ADD COLUMN IF NOT EXISTS cliente_documento text DEFAULT '',
  ADD COLUMN IF NOT EXISTS cliente_endereco text DEFAULT '',
  ADD COLUMN IF NOT EXISTS laudo_relatorio  text DEFAULT '',
  ADD COLUMN IF NOT EXISTS tecnico          text DEFAULT '',
  ADD COLUMN IF NOT EXISTS obs              text DEFAULT '';

-- Colunas extras na tabela receitas
ALTER TABLE public.receitas
  ADD COLUMN IF NOT EXISTS origem          text DEFAULT 'manual',
  ADD COLUMN IF NOT EXISTS nf_xml_ref      text DEFAULT '',
  ADD COLUMN IF NOT EXISTS nf_xml_filename text DEFAULT '';
```

---

## 🚀 Deploy

O deploy é **automático via GitHub Pages**. Qualquer commit na branch `main` atualiza o sistema em produção em 1–3 minutos.

```bash
# Atualizar o sistema
git add index.html
git commit -m "feat: descrição da melhoria"
git push origin main
# Aguardar ~2 minutos → erp.idealtech.srv.br atualizado
```

---

## 📁 Estrutura

```
idealtech-erp/
├── index.html    # Aplicação completa (single-file app ~8.500 linhas)
├── CNAME         # Domínio customizado → erp.idealtech.srv.br
└── README.md     # Este arquivo
```

---

## ⚙️ Configuração Inicial (novo usuário)

1. Acesse [erp.idealtech.srv.br](https://erp.idealtech.srv.br)
2. Crie uma conta com e-mail e senha
3. Confirme o e-mail recebido
4. Vá em **⚙️ Config** e preencha os dados da empresa
5. As 15 categorias padrão são criadas automaticamente

---

## 👨‍💻 Desenvolvido por

**IdealTech** — Gestão e Tecnologia

🌐 [idealtech.srv.br](https://idealtech.srv.br) · 📧 idealtech.get@gmail.com

---

<div align="center">
<sub>© 2026 IdealTech — Todos os direitos reservados</sub>
</div>
