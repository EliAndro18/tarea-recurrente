# Corrida 2

## Caso procesado

| orden | partida | nombre_archivo | importe_ABL | codigo_pago_electronico | estado |
|---|---|---|---|---|---|
| 2 | ••••818 | ABL_••••818_09-2026.pdf | 28339.44 | •••••••••8186 | OK |

## Resultado

Procesadas: 1/1 — OK: 1, Pendientes: 0, Error: 0.

La boleta fue descargada y el Excel fue actualizado con el nombre del archivo,
el importe y el código de pago.

## Incidencias

El nombre del archivo se escribió en una columna G nueva, aunque el archivo
original ya destinaba la columna C para ese dato.

## Verificaciones

- [x] PDF descargado.
- [x] Excel completado con el resultado.
- [x] Importe obtenido de la boleta.
- [x] Código de pago obtenido de la boleta.
- [x] Partida y código anonimizados en este archivo.
