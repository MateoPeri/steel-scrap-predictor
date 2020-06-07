# Pasos seguidos en el proyecto

## Carga y procesado de datos
Los datos están en un [archivo .zip](/data/raw.zip) en este repositorio. Los descargamos con ```wget``` y descomprimimos el archivo.
Para entrenar solo nos interesan los archivos de 'Closing Prices'.
Los de 'Final Settlement' los usaremos para evaluar la precisión del modelo.
Cargamos cada archivo en un ```DataFrame``` de Pandas y nos quedamos con la fecha y la columna ```M1```.
En el caso de HU, hay que hacer una conversión, ya que los datos vienen en USD/st (tonelada corta),
mientras que los demás archivos tienen USD/mt (tonelada métrica). Aplicamos la siguiente función para pasar de una unidad a otra.
```py
def st_to_mt(st):
  return st/1.10231131
```
Hay datos de SC y SR desde el 23-11-2015, pero los datos de HC y HU no empiezan hasta el 11-03-2019. Desde esa fecha hasta la última entrada sólo hay 292 datos.

Son muy pocos datos para poder entrenar un modelo y hacer predicciones fiables.
En efecto, cuando hacermos un modelo con Prophet, obtenemos un 93% de precisión.
Con tan pocos datos, el modelo ha 'memorizado' (overfitting), y al hacer la predicción salen valores extraños.
