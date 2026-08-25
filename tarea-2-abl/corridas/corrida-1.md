# Corrida 1

## Caso procesado

| orden | partida | nombre_archivo | importe_ABL | codigo_pago_electronico | estado |
|---|---|---|---|---|---|
| 1 | ••••816 | ABL_••••816_09-2026.pdf | 35948.94 | •••••••••8169 | OK |

## Resultado

Procesadas: 1/1 — OK: 1, Pendientes: 0, Error: 0.

La boleta fue descargada y la salida estructurada fue generada, pero el Excel
no quedó completado con el nombre del archivo, el importe y el código de pago.

## Incidencias

La opción “Histórico de boletas” redirigió inesperadamente al Portal del
Contribuyente; se descartó ese flujo y se repitió la consulta desde el enlace
público indicado. El visor integrado bloqueó la previsualización del PDF, pero
el archivo se descargó desde el enlace generado por AGIP y se validó como un
PDF legible de una página.

## Verificaciones

- [x] PDF descargado y legible.
- [ ] Excel completado con el resultado.
- [x] Importe obtenido de la boleta.
- [x] Código de pago obtenido de la boleta.
- [x] Partida y código anonimizados en este archivo.
