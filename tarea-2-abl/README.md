# Tarea 2 — Creación de agentes de IA

## Descripción de la tarea recurrente

La entrega documenta un agente que procesa periódicamente partidas
inmobiliarias, consulta la boleta de ABL correspondiente al período solicitado,
descarga el PDF y registra el resultado en una planilla de control.

## Objetivo del agente

El objetivo es obtener datos verificables directamente de cada boleta y dejar
un registro estructurado, comparable y auditable, sin inventar importes ni
códigos de pago cuando la consulta no pueda completarse.

## Estructura de la entrega

- `system_prompt.md`: rol, contexto, restricciones y formato general.
- `user_prompt.md`: tarea puntual, mapeo de salida y ejemplos ficticios.
- `corridas/`: resultados anonimizados de las tres ejecuciones.
- `datos/`: planilla real de trabajo, conservada únicamente en forma local.
- `boletas/`: PDF reales descargados, conservados únicamente en forma local.
- `.gitignore`: reglas que excluyen planillas y boletas privadas.

## Corrida 1

La primera corrida descargó la boleta y generó la salida estructurada. También
registró una redirección inesperada desde “Histórico de boletas” y un bloqueo
del visor integrado, que se resolvió utilizando el enlace generado por AGIP.

### Problema observado

El agente descargó la boleta y generó la salida estructurada, pero no completó
el Excel con el nombre del archivo descargado, el importe y el código de pago
LINK/BANELCO.

## Iteración 1

### Pieza modificada

Se modificó únicamente la sección `## Tarea` de `user_prompt.md`.

### Cambio realizado

Se indicó expresamente que, después de descargar cada boleta, el agente debía
actualizar el Excel local con el nombre exacto del PDF, el importe de la cuota
y el código de pago LINK/BANELCO.

### Resultado efectivo en la corrida 2

El agente descargó la segunda boleta y completó el Excel con los tres datos
requeridos. Sin embargo, creó una columna G para el nombre del archivo en lugar
de utilizar la columna ya prevista por la planilla.

## Corrida 2

La segunda corrida produjo una salida estructurada comparable, descargó la
boleta y actualizó el Excel.

### Problema observado

El agente creó una columna nueva llamada `Nombre del archivo` en la columna G,
pero el archivo original ya destinaba la columna C, titulada
`CUOTA 09- VTO 21/09/2026`, para registrar el nombre de la boleta descargada.

## Iteración 2

### Pieza modificada

Se modificó únicamente el formato/mapeo de salida de `user_prompt.md`.

### Cambio realizado

Se estableció expresamente que el nombre exacto del PDF debía escribirse en la
columna C: `CUOTA 09- VTO 21/09/2026`.

### Resultado efectivo en la corrida 3

Los nombres de las tres boletas quedaron en la columna C, los importes en la
columna D y los códigos LINK/BANELCO en la columna E. Se retiró el contenido
agregado en la columna G, se conservaron las fórmulas existentes y el total se
calculó correctamente.

## Corrida 3

La tercera boleta fue descargada y verificada contra los valores escritos en
el Excel. El resultado final dejó completas las tres filas en las columnas
previstas, sin completar la fecha de pago y manteniendo la fórmula del total.

## Limitación externa: reCAPTCHA

El agente pudo continuar cuando la sesión o el control de verificación lo
permitieron. Un desafío que exija explícitamente una verificación humana y que
impida avanzar podría requerir intervención manual, por tratarse de un control
externo al agente.

## Privacidad

El Excel con partidas reales y los PDF de las boletas se mantienen localmente.
Ambos tipos de archivo están excluidos del repositorio mediante `.gitignore`.
Las corridas publicables muestran únicamente fragmentos enmascarados de las
partidas y de los códigos de pago.

## Ajuste editorial de privacidad

Después de completar las corridas, los números utilizados como ejemplos en los
prompts se etiquetaron inequívocamente como datos ficticios o se reemplazaron
por marcadores. Este cambio es exclusivamente editorial: no altera reglas,
pasos, formato ni lógica operativa, y no constituye una tercera iteración del
contrato.

## Reflexión final

Aprendí que una instrucción general no garantiza que el agente complete el
archivo de trabajo: la acción debe pedirse expresamente. También comprobé que
el mapeo exacto de columnas debe quedar indicado para evitar que el agente
cree una estructura paralela. Las salidas estructuradas facilitaron la
comparación entre corridas y permitieron observar el efecto de cada mejora.

Al mismo tiempo, los controles externos pueden impedir una automatización
completamente desatendida y requerir intervención humana. Finalmente, proteger
los datos reales no es una tarea posterior: forma parte del diseño del agente,
de sus salidas y de la forma en que se prepara la entrega.
