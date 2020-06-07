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
