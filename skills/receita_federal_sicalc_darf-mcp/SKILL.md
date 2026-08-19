---
name: receita_federal_sicalc_darf-mcp
description: Skill da REST API do Receita Federal SICALC: Gerar DARF na MCP.AI: 1 endpoint em /api/receita_federal_sicalc_darf. Receita Federal SICALC: Gerar DARF, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Receita Federal SICALC: Gerar DARF — REST API skill

Você tem acesso à **Receita Federal SICALC: Gerar DARF** REST API na MCP.AI.

> Receita Federal SICALC: Gerar DARF, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/receita_federal_sicalc_darf
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/receita_federal_sicalc_darf/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"valor_principal":"...","periodo_apuracao":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/receita_federal_sicalc_darf/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `receita_federal_sicalc_darf_consultar`

Receita Federal SICALC: Gerar DARF, consulta em fonte oficial. _(POST /api/receita_federal_sicalc_darf/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `cnpj` | string | Não | Parâmetro de consulta "cnpj". |
| `cpf` | string | Não | Parâmetro de consulta "cpf". |
| `birthdate` | string | Não | Parâmetro de consulta "birthdate". |
| `observacoes` | string | Não | Parâmetro de consulta "observacoes". |
| `codigo` | string | Não | Parâmetro de consulta "codigo". |
| `valor_principal` | string | Sim | Parâmetro de consulta "valor_principal". |
| `periodo_apuracao` | string | Sim | Parâmetro de consulta "periodo_apuracao". |
| `data_consolidacao` | string | Não | Parâmetro de consulta "data_consolidacao". |
| `numero_referencia` | string | Não | Parâmetro de consulta "numero_referencia". |
| `quota` | string | Não | Parâmetro de consulta "quota". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_receita_federal_sicalc_darf` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
