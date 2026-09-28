# Vikings Go To Hollywood WildFight RushingWilds

Provider: **Yggdrasil**  
Game ID: `10964`  
Estado: **COMPLETED** en demo.

## Endpoint principal

```http
POST https://demo.yggdrasilgaming.com/game.web/service?fn=play
Content-Type: application/x-www-form-urlencoded
```

## Compra 1 — 10 Free Spins

```text
channel=pc
channelID=
channelSuffix=
currency=EUR
lang=en
gameid=10964
gameHistorySessionId=session
gameHistoryTicketId=ticket
amount=65
coin=0.1
cmd=BB_2
clientinfo=<dynamic>
```

Respuesta observada:

- HTTP `200`
- `code=0`
- `bet.status=RESULTED`
- `awardSpins.value=10`
- `berzerkSymbols=[]`
- contador de free spins: `9,8,7,6,5,4,3,2,1,0`
- termina con `finishSpins`
- no hubo un segundo `POST fn=play`
- no apareció ninguna elección intermedia

Resultado de esta corrida demo: `17.80 EUR`. El resultado es aleatorio y no forma parte del contrato.

## Compra 2 — 10 Free Spins + 1 Berzerk

```text
channel=pc
channelID=
channelSuffix=
currency=EUR
lang=en
gameid=10964
gameHistorySessionId=session
gameHistoryTicketId=ticket
amount=390
coin=0.1
cmd=BB_5
clientinfo=<dynamic>
```

Respuesta observada:

- HTTP `200`
- `code=0`
- `bet.status=RESULTED`
- `awardSpins.value=10`
- `berzerkSymbols=["H3"]`
- contador de free spins: `9,8,7,6,5,4,3,2,1,0`
- termina con `finishSpins`
- no hubo un segundo `POST fn=play`
- no apareció ninguna elección intermedia

Resultado de esta corrida demo: `97.80 EUR`. El resultado es aleatorio.

## Qué significa para el port

La compra completa se resuelve en servidor con **un único POST**. La respuesta contiene una lista de `clientData.actions` que describe la secuencia que la UI debe reproducir: reels, WildFight, contadores, multiplicadores, premios y `finishSpins`.

Por lo observado, no hay que solicitar individualmente cada free spin al servidor para estas compras.

`clientinfo` y el estado/cookies de sesión son dinámicos. No deben hardcodearse.

## Bootstrap observado

```http
POST https://demo.yggdrasilgaming.com/game.web/service?fn=authenticate&org=Demo
GET  https://demo.yggdrasilgaming.com/game.web/service?fn=clientinfo...
GET  https://demo.yggdrasilgaming.com/game.web/service?fn=game&org=Demo&gameid=10964&currency=EUR
GET  https://demo.yggdrasilgaming.com/game.web/service?fn=restore
```

## Evidencia

- `observed.json`: contrato normalizado.
- `raw/buy-bb2.json`: request y respuesta normalizada de `BB_2`.
- `raw/buy-bb5.json`: request y respuesta normalizada de `BB_5`.
- `.github/workflows/capture-yggdrasil-10964.yml`: captura reproducible contra la demo.

Los archivos `raw/` conservan los campos semánticos relevantes del response. Los símbolos/line wins aleatorios pueden regenerarse ejecutando el workflow de captura.
