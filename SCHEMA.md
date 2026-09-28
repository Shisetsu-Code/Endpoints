# Esquema de registro

Cada `observed.json` usa este formato conceptual:

```json
{
  "provider": "",
  "game": {
    "name": "",
    "id": "",
    "source_url": ""
  },
  "session": {
    "bootstrap": [],
    "dynamic_fields": []
  },
  "actions": [
    {
      "name": "",
      "status": "OBSERVED|CAUSAL|COMPLETED|PARTIAL|UNKNOWN",
      "request": {
        "method": "",
        "url": "",
        "content_type": "",
        "body_format": "",
        "body": {}
      },
      "response": {
        "status": null,
        "content_type": "",
        "body": null
      },
      "continuation": [],
      "choices": []
    }
  ]
}
```

Reglas:
1. Nunca reutilizar tokens, cookies o identificadores de sesión como constantes.
2. Marcar como dinámico todo valor generado por sesión/round.
3. Guardar el body de respuesta cuando sea legible.
4. Si una compra abre una selección posterior, registrar cada opción como rama distinta.
5. Una compra sólo queda `COMPLETED` cuando vuelve a estado base o el servidor indica finalización inequívoca.
