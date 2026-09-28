# 3 Piggies of Bank

Provider: **Yggdrasil**  
Game ID: `10945`  
Status: **COMPLETED** on the public demo.

## Endpoint

```http
POST https://demo.yggdrasilgaming.com/game.web/service?fn=play
Content-Type: application/x-www-form-urlencoded
```

## Verified purchases at EUR 1 base bet

| Purchase | UI cost | cmd | amount | coin | Completion |
| --- | ---: | --- | ---: | ---: | --- |
| Double | €180 | `BB_BLUE` | 180 | 180 | `isFinished=true` |
| Collect | €120 | `BB_GREEN` | 120 | 120 | `isFinished=true` |
| Mystery | €150 | `BB_RED` | 150 | 150 | `isFinished=true` |
| Random Bank | €150 | `BB_RANDOM` | 150 | 150 | `isFinished=true` |
| All Banks | €250 | `BB_ALL` | 250 | 250 | `isFinished=true` |

All five returned HTTP 200 with `code=0`.

No intermediate player choice was observed. Random Bank resolves the bank server-side. All Banks returns red, green and blue bonus actions in the same response.

The responses expose `nextCmds="C"`, but the purchased feature itself is already marked finished in the same response.

## Base spin

```text
cmd=BASIC
amount=1
coin=1
```

## Raw evidence

```
raw/double.json
raw/collect.json
raw/mystery.json
raw/random-bank.json
raw/all-banks.json
```

Sensitive authentication/cookie headers are redacted. Session-generated fields such as `clientinfo`, `wagerid`, `userId`, `x-csid` and `x-crid` are dynamic.
