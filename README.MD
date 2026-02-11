# 📚 Google Classroom Automation (Google Apps Script)

Este projeto contém **dois scripts em Google Apps Script** para automação acadêmica:

1. **Criação em massa de turmas no Google Classroom**
2. **Convite de múltiplos professores por seção**

Os scripts utilizam dados de uma **planilha Google Sheets** como fonte.

---

## ⚙️ Requisitos

Antes de usar:

- Conta Google com permissão para:
  - Criar cursos no Google Classroom
  - Convidar professores
- Planilha Google Sheets
- Apps Script vinculado à planilha
- Serviço avançado **Google Classroom API** ativado

### ✅ Ativar Classroom API

No Apps Script:

1. `Serviços → Serviços Avançados do Google`
2. Ativar **Google Classroom API**
3. Confirmar também no Google Cloud Console

---

# 🏫 SCRIPT 1 — Criação de Turmas

Cria turmas automaticamente com base nos dados da planilha.

## 📄 Estrutura da Planilha

| Coluna | Campo         |
| ------ | ------------- |
| A      | Nome          |
| B      | Seção         |
| C      | Sala          |
| D      | Descrição     |
| E      | Código (auto) |

> O código de inscrição será preenchido automaticamente na **coluna E**.

---

## ▶️ Como Usar

1. Abra a planilha
2. Menu **Custom → Create Classroom**
3. As turmas serão criadas
4. O código de inscrição aparecerá na coluna E

---

## 🧠 Funcionamento

- Lê dados a partir da linha 2
- Cria cursos via `Classroom.Courses.create()`
- Retorna `enrollmentCode`

---

# 👩‍🏫 SCRIPT 2 — Convidar Professores

Convida **múltiplos professores** para turmas já existentes.

## 📄 Estrutura da Planilha

| Coluna | Campo              |
| ------ | ------------------ |
| A      | (Livre)            |
| B      | Seção da Turma     |
| C      | (Livre)            |
| D      | (Livre)            |
| E      | (Livre)            |
| F      | Emails Professores |

---

## ✉️ Formato dos Emails

Na coluna **F**, use:
