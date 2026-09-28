# Endpoints

Repositorio de evidencia de protocolos de juego capturados desde demos públicas.

Objetivo:
- registrar endpoints por proveedor y juego;
- documentar método, Content-Type y payload exacto;
- separar campos constantes de campos dinámicos;
- guardar request y response observados;
- recorrer compras/bonus hasta su finalización;
- anotar elecciones intermedias cuando existan;
- conservar evidencia suficiente para contrastar un port contra el servidor original.

## Convención

Cada juego vive en:

```
providers/<provider>/<game-id>-<slug>/
  README.md
  observed.json
```

Estados:
- `OBSERVED`: capturado del cliente real.
- `CAUSAL`: acción UI -> request identificada.
- `COMPLETED`: la feature/compra fue recorrida hasta volver al juego base.
- `PARTIAL`: falta cerrar alguna rama.
- `UNKNOWN`: no demostrado.

No se consideran válidos endpoints o comandos inferidos sin tráfico real.
