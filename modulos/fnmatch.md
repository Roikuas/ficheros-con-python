
# Mapa Mental Completo: Módulo `fnmatch` en Python

## fnmatch
- Comparación de nombres de archivo con patrones
- Patrones estilo Unix

### Funciones Principales

#### fnmatch()
- Compara un nombre de archivo con un patrón
- Sintaxis: `fnmatch.fnmatch(filename, pattern)`
- Parámetros:
  - `filename`: Nombre del archivo a comparar
  - `pattern`: Patrón para comparar el nombre del archivo
- Devuelve: `True` si el nombre del archivo coincide con el patrón, de lo contrario `False`

#### fnmatchcase()
- Compara un nombre de archivo con un patrón usando coincidencia sensible a mayúsculas y minúsculas
- Sintaxis: `fnmatch.fnmatchcase(filename, pattern)`
- Parámetros:
  - `filename`: Nombre del archivo a comparar
  - `pattern`: Patrón para comparar el nombre del archivo
- Devuelve: `True` si el nombre del archivo coincide con el patrón, de lo contrario `False`

#### filter()
- Filtra una lista de nombres de archivo, manteniendo solo aquellos que coinciden con un patrón
- Sintaxis: `fnmatch.filter(names, pattern)`
- Parámetros:
  - `names`: Lista de nombres de archivo
  - `pattern`: Patrón para filtrar los nombres de archivo
- Devuelve: Lista de nombres de archivo que coinciden con el patrón

#### translate()
- Traduce un patrón en una expresión regular
- Sintaxis: `fnmatch.translate(pattern)`
- Parámetros:
  - `pattern`: Patrón a traducir
- Devuelve: Cadena que representa la expresión regular correspondiente al patrón

### Comodines
- **`*`**: Coincide con cero o más caracteres
- **`?`**: Coincide con un solo carácter
- **`[abc]`**: Coincide con cualquiera de los caracteres entre corchetes
- **`[!abc]`**: Coincide con cualquiera de los caracteres que no están entre corchetes
- **`[a-z]`**: Coincide con cualquier carácter en el rango especificado

### Ejemplos de Uso
`import fnmatch`

#### Uso de fnmatch
```python
# Comparar un nombre de archivo con un patrón
print(fnmatch.fnmatch('archivo.txt', '*.txt'))  # True
print(fnmatch.fnmatch('archivo.py', '*.txt'))   # False
```
#### Uso de fnmatchcase
```python
# Comparar un nombre de archivo con un patrón (sensible a mayúsculas y minúsculas)
print(fnmatch.fnmatchcase('Archivo.TXT', '*.txt'))  # False
print(fnmatch.fnmatchcase('Archivo.TXT', '*.TXT'))  # True
```
#### Uso de filter
```python
# Filtrar una lista de nombres de archivo
archivos = ['data1.txt', 'data2.csv', 'image.png', 'script.py']
filtrados = fnmatch.filter(archivos, '*.txt')
print(filtrados)  # ['data1.txt']
```
#### Uso de translate
```python
# Traducir un patrón en una expresión regular
regex = fnmatch.translate('*.txt')
print(regex)  # '.*\.txt\Z(?ms)'
```

### Aplicaciones Comunes

#### Filtrado de Nombres de Archivo en Directorios
```python
import os
# Listar archivos .py en el directorio actual
archivos_py = fnmatch.filter(os.listdir('.'), '*.py')
print(archivos_py)
```
#### Validación de Patrones en Nombres de archivo
```python
# Validar nombres de archivo
nombres = ['test1.py', 'test2.TXT', 'data.csv']
patron = '*.txt'
validados = [nombre for nombre in nombres if fnmatch.fnmatch(nombre, patron)]
print(validados)  # ['test2.TXT']

```


