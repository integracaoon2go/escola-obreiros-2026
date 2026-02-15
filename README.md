# 🚀 Sistema de Publicação Automatizada - Escola de Obreiros 2026

> **Status:** ✅ Em Produção | **v1.0**

Este projeto automatiza a publicação de novos módulos educacionais no site da Escola de Obreiros 2026, integrando **Telegram**, **GitHub Pages** e **Discord** através do **n8n**.

---

## 🎯 Objetivo
Permitir que administradores publiquem novos conteúdos no site institucional sem precisar editar código HTML manualmente. Basta enviar uma mensagem formatada no Telegram.

**🔗 Links:**
- **Site ao vivo:** [https://integracaoon2go.github.io/escola-obreiros-2026/](https://integracaoon2go.github.io/escola-obreiros-2026/)
- **Repositório:** `integracaoon2go/escola-obreiros-2026`

---

## 🏗️ Arquitetura do Sistema

| Componente | Função |
| :--- | :--- |
| **n8n** | Orquestrador do Workflow (Cérebro) |
| **Telegram Bot** | Trigger (Entrada de Dados) |
| **GitHub API** | Armazenamento e Versionamento (OAuth2) |
| **GitHub Pages** | Hospedagem do Site (Frontend) |
| **Discord** | Notificações para a Equipe |

---

## 🔄 Fluxo de Funcionamento

```mermaid
graph TD
    A[📱 Telegram Bot] -->|Mensagem Formatada| B(⚙️ n8n: Validação e Análise)
    B -->|Extrai Dados| C{Baixa index.html do GitHub}
    C -->|HTML Base| D[🛠️ Injeta Card HTML]
    D -->|Antes do módulo 'Em Breve'| E[🐙 GitHub: Commit + Push]
    E -->|Deploy Automático| F[🌐 Site Atualizado]
    E --> G[✅ Confirmação Telegram]
    E --> H[📢 Notificação Discord]
