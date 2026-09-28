# Gemstone Jam

Game ID: `10852`

No se observó botón BUY en el cliente demo. Se capturó el spin base.

```http
POST https://demo.yggdrasilgaming.com/game.web/service?fn=play
Content-Type: application/x-www-form-urlencoded
```

```text
cmd=BASIC
amount=1
coin=1
gameid=10852
clientinfo=<dynamic>
```

Respuesta observada: HTTP 200, code=0, client_is_finished=True.
Response completa: `raw/base-spin.json`.
