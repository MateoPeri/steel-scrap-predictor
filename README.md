# Predicción del precio de la chatarra de acero

## Definiciones

### Conceptos:
- **Volumen**: Cantidad de transacciones realizadas en un periodo de tiempo concreto.
- **Interés Abierto**: Cantidad de transacciones abiertas (es decir, que todavía no se han realizado). Sería la cantidad de metal a la venta cada día.

### Metales
- **SC:** Steel Scrap (chatarra de acero)
- **SR:** Steel Rebar (barras de acero)
- **HC:** Hot Rolled Coil China (bobina laminada en caliente, procedente de China)
- **HU:** Hot Rolled Coild US (bobina laminada en caliente, procedente de EEUU)

### Datos
- **Closing Prices**: Predicciones hasta 15 meses vista del precio de cada metal, cada día.
- **CSF TV**: Contiene datos de volumen a partir de 2017.
- **CSF EOI**: Datos de interés abierto desde 2017.

## Objetivo
Predecir el precio de SC a partir de datos históricos de los demás tipos de metal.
