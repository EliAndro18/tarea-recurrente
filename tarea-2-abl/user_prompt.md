# User Prompt — Pedido puntual

## Tarea
Procesá las siguientes partidas inmobiliarias para el período **09-2026**
(septiembre 2026). Para cada una:
1. Entrá a AGIP y descargá la boleta de ABL correspondiente.
2. Completá una fila de la tabla con el resultado, siguiendo el formato y las
   restricciones del system prompt.
3. Después de descargar cada boleta, actualizá el Excel local con el nombre
   exacto del archivo PDF descargado, el importe de la cuota y el código de
   pago LINK/BANELCO.

Partidas a procesar (orden, partida):

**DATOS FICTICIOS**

| orden | partida |
|---|---|
| 1 | `<PARTIDA_FICTICIA_1>` |
| 2 | `<PARTIDA_FICTICIA_2>` |
| 3 | `<PARTIDA_FICTICIA_3>` |

*(Reemplazar esta lista por el extracto real de tu Excel de partidas en cada
corrida — usá entre 5 y 10 partidas por corrida para poder revisar el
resultado a mano.)*

## Mapeo de salida en Excel

- El nombre exacto del archivo PDF descargado debe escribirse en la columna C:
  `CUOTA 09- VTO 21/09/2026`.

## Ejemplos de fila esperada

Los siguientes ejemplos usan **DATOS FICTICIOS**.

Caso resuelto sin problemas:

| orden | partida | nombre_archivo | importe_ABL | codigo_pago_electronico | estado |
|---|---|---|---|---|---|
| 1 | `<PARTIDA_FICTICIA_1>` | `ABL_<PARTIDA_FICTICIA_1>_09-2026.pdf` | 15230.50 | `<CODIGO_FICTICIO>` | OK |

Caso bloqueado (sin inventar datos):

| orden | partida | nombre_archivo | importe_ABL | codigo_pago_electronico | estado |
|---|---|---|---|---|---|
| 2 | `<PARTIDA_FICTICIA_2>` | — | — | — | ERROR (captcha no resuelto tras 2 intentos) |
