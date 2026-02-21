# Mini SOC — Security Monitoring App

Projeto educacional para construir um **Mini SOC (Security Operations Center)** focado em ingestão, análise e visualização de logs de segurança em formato JSON.

## 🎯 Objetivo
Receber logs de aplicações/sistemas, aplicar regras simples de detecção de eventos suspeitos e exibir alertas em um dashboard web.

## 🧩 Escopo (MVP)
- Ingestão de logs via API (JSON)
- Regras básicas de detecção (ex: falhas de login, acessos suspeitos)
- Persistência de logs e alertas
- Dashboard web simples
- Exportação de incidentes

## 🏗️ Arquitetura (alto nível)
Client (Frontend) ⇄ API (Backend) ⇄ Banco de Dados

## 📁 Estrutura do repositório
- `docs/` — documentação técnica do projeto
- `backend/` — API e regras de detecção (futuro)
- `frontend/` — dashboard web (futuro)
- `infra/` — arquivos de deploy e containers (futuro)

## 📄 Documentação
Veja a pasta [`docs/`](./docs) para:
- Proposta do projeto
- Formato de logs
- Regras de detecção

## 🚧 Status
Projeto em desenvolvimento (MVP).