
# Regras de Detecção — Mini SOC

Este documento descreve as **regras de detecção do MVP**.

## Regra-001 — Falhas de login repetidas

- **Descrição**: múltiplas falhas de login a partir do mesmo IP
- **Condição**: mais de 5 falhas em 5 minutos
- **Evento**: login_failed
- **Severidade**: high

---

## Regra-002 — Login fora do horário esperado

- **Descrição**: login bem-sucedido fora do horário comercial
- **Condição**: login_success entre 22h e 6h
- **Severidade**: medium

---

## Regra-003 — Acesso a endpoint sensível

- **Descrição**: acesso a endpoints administrativos
- **Condição**: event_type = admin_access
- **Severidade**: high