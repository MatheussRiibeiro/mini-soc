# Ingest API — Mini SOC

Este documento define o contrato do endpoint responsável pela ingestão
de logs de segurança no Mini SOC.


## Endpoint

**POST** `/api/ingest`

Responsável por receber eventos de segurança no formato JSON.


## Autenticação

- Tipo: API Key ou JWT (definição MVP)
- Header obrigatório:
 `Authorization: Bearer <token>`  
Onde `<token>` pode ser uma API Key ou um JWT (definição MVP).


## Regras de validação

A API deve rejeitar logs que:

- não estejam em JSON válido
- não possuam os campos obrigatórios
- tenham severity fora do padrão
- não contenham header de autenticação



## Exemplo de requisição HTTP 

```http
POST /api/ingest HTTP/1.1
Host: mini-soc.io
Authorization: Bearer <token>
Content-Type: application/json

{
  "event_type": "login_failed",
  "ip": "192.168.1.10"
}


## Payload esperado (JSON)

```json
{
  "timestamp": "2026-02-21T14:32:00Z",
  "source": "auth_service",
  "host": "server-01",
  "event_type": "login_failed",
  "user": "jdoe",
  "ip": "192.168.1.10",
  "severity": "high",
  "message": "Failed login attempt"
}

## Campos obrigatórios

- `timestamp` deve estar no formato ISO-8601
- `event_type` é obrigatório
- `ip` deve ser um IPv4 ou IPv6 válido
- `severity` aceita apenas: `low`, `medium`, `high`
- Payloads fora do padrão devem ser rejeitados


### Sucesso
**201 Created**
```json
{
  "status": "ok",
  "message": "Log ingested successfully"
}

**400 Bad Request**
{
  "status": "error",
  "detail": "Invalid payload format"
}
**401 Unauthorized**
{
  "status": "error",
  "detail": "Invalid or missing token"
}