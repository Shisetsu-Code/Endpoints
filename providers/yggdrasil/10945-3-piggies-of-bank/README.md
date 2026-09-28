# 3 Piggies of Bank

Game ID: `10945`

## Endpoint

```http
POST https://demo.yggdrasilgaming.com/game.web/service?fn=play
Content-Type: application/x-www-form-urlencoded
```

## Acciones observadas

### buy-double

```text
cmd=BB_BLUE
amount=180
coin=180
gameid=10945
clientinfo=<dynamic>
```
Respuesta: HTTP 200, code=0, bet_status=RESULTED, nextCmds=C, client_is_finished=True.
Response completa: `raw/buy-double.json`.

### buy-collect

```text
cmd=BB_GREEN
amount=120
coin=120
gameid=10945
clientinfo=<dynamic>
```
Respuesta: HTTP 200, code=0, bet_status=RESULTED, nextCmds=C, client_is_finished=True.
Response completa: `raw/buy-collect.json`.

### buy-mystery

```text
cmd=BB_RED
amount=150
coin=150
gameid=10945
clientinfo=<dynamic>
```
Respuesta: HTTP 200, code=0, bet_status=RESULTED, nextCmds=C, client_is_finished=True.
Response completa: `raw/buy-mystery.json`.

### buy-random-bank

```text
cmd=BB_RANDOM
amount=150
coin=150
gameid=10945
clientinfo=<dynamic>
```
Respuesta: HTTP 200, code=0, bet_status=RESULTED, nextCmds=C, client_is_finished=True.
Response completa: `raw/buy-random-bank.json`.

### buy-all-banks

```text
cmd=BB_ALL
amount=250
coin=250
gameid=10945
clientinfo=<dynamic>
```
Respuesta: HTTP 200, code=0, bet_status=RESULTED, nextCmds=C, client_is_finished=True.
Response completa: `raw/buy-all-banks.json`.

