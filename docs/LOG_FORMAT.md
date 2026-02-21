# Log Format — Mini SOC

Este documento define o **contrato oficial de logs** aceitos pelo Mini SOC.
Qualquer mudança neste formato deve ser discutida antes de implementação.

## Estrutura base (JSON)

```json
{
  "timestamp": "ISO-8601",
  "source": "string",
  "host": "string",
  "event_type": "string",
  "user": "string",
  "ip": "string",
  "severity": "low | medium | high",
  "message": "string"
}

Descrição dos campos

timestamp: data/hora do evento

source: origem do log (app, firewall, auth)

host: máquina ou serviço de origem

event_type: tipo do evento (ex: login_failed)

user: usuário envolvido (se aplicável)

ip: endereço IP de origem

severity: severidade avaliada

message: descrição textual do evento