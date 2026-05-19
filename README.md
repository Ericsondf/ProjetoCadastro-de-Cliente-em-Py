# 🏪 Atlas Toldos — Sistema de Gestão de Clientes

Sistema completo para cadastro, gestão de clientes e orçamentos, com sincronização na nuvem.

---

## ✅ Funcionalidades

- **Cadastro completo de clientes** — dados pessoais, endereço, histórico
- **Ligações de recompra automáticas** — alerta após 3 anos (configurável)
- **Orçamentos para visitas** — tipo de toldo, dimensões, cores, mecanismo, valor
- **Dashboard** com métricas e próximas ligações
- **Sincronização com nuvem** via Supabase (gratuito)
- **Banco de dados local** — funciona offline

---

## 🚀 Como Instalar (Windows)

### Passo 1 — Instalar Python
1. Acesse [python.org/downloads](https://python.org/downloads)
2. Clique em "Download Python"
3. **IMPORTANTE:** Marque ✅ "Add Python to PATH" antes de instalar

### Passo 2 — Extrair os arquivos
- Extraia a pasta `atlas-toldos` em qualquer local do seu computador (ex: `C:\atlas-toldos`)

### Passo 3 — Iniciar o sistema
- Clique duplo em **INICIAR.bat**
- O navegador abrirá automaticamente em `http://localhost:5000`

---

## ☁️ Configurar Sincronização na Nuvem (Gratuito)

Para que os dados subam para a nuvem automaticamente:

1. Acesse [supabase.com](https://supabase.com) e crie uma conta gratuita
2. Crie um **novo projeto**
3. Vá em **Settings → API**
4. Copie:
   - **Project URL** (ex: `https://abcdefg.supabase.co`)
   - **anon public key** (chave longa começando com `eyJ...`)
5. No sistema, vá em **Configurações** e cole as informações
6. Clique em **"Sincronizar Nuvem"** na barra lateral sempre que quiser enviar os dados

### Criar a tabela no Supabase
No painel do Supabase, vá em **SQL Editor** e execute:

```sql
CREATE TABLE IF NOT EXISTS clientes (
  id BIGINT PRIMARY KEY,
  nome TEXT,
  telefone TEXT,
  email TEXT,
  cpf TEXT,
  endereco TEXT,
  bairro TEXT,
  cidade TEXT,
  cep TEXT,
  data_cadastro TEXT,
  data_instalacao TEXT,
  data_proxima_ligacao TEXT,
  status TEXT,
  observacoes TEXT,
  criado_em TEXT
);
```

---

## 📁 Estrutura de Arquivos

```
atlas-toldos/
├── INICIAR.bat          ← Clique aqui para abrir o sistema
├── server.py            ← Servidor da aplicação
├── atlas_toldos.db      ← Banco de dados local (criado automaticamente)
├── README.md            ← Este arquivo
└── public/
    └── index.html       ← Interface do sistema
```

---

## ⚙️ Configurações

No menu **Configurações** do sistema você pode:
- Alterar o número de **anos para recompra** (padrão: 3 anos)
- Configurar as credenciais do Supabase para sincronização

---

## 💡 Dicas de Uso

- **Cor vermelha** na data de ligação = ligação atrasada
- **Cor laranja** = ligação nos próximos 60 dias
- **Cor dourada** = ligação futura normal
- Use o campo **Observações do Orçamento** para deixar instruções ao vendedor antes da visita

---

Desenvolvido para Atlas Toldos 🏪
