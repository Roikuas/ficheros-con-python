
# Mapa Mental Completo: Módulo `csv` en Python

## csv
- Manipulación de archivos CSV (Comma-Separated Values)
- Lectura y escritura de datos tabulares

### Funciones Principales

#### Lectura de Archivos CSV

- **csv.reader()**
  - Lee un archivo CSV línea por línea
  - Sintaxis: `csv.reader(archivo, delimiter=',')`
    - `archivo`: Objeto de archivo abierto o iterable de líneas CSV
    - `delimiter`: Carácter delimitador de campos (por defecto `,`)
  - Ejemplo:
    ```python
    import csv
    
    with open('datos.csv', 'r') as archivo_csv:
        lector_csv = csv.reader(archivo_csv)
        for fila in lector_csv:
            print(fila)
    ```

#### Escritura en Archivos CSV

- **csv.writer()**
  - Escribe filas en un archivo CSV
  - Sintaxis: `csv.writer(archivo, delimiter=',', quoting=csv.QUOTE_MINIMAL)`
    - `archivo`: Objeto de archivo abierto para escribir
    - `delimiter`: Carácter delimitador de campos (por defecto `,`)
    - `quoting`: Tipo de cotización para campos que contienen caracteres especiales (por defecto `csv.QUOTE_MINIMAL`)
  - Ejemplo:
    ```python
    import csv
    
    datos = [
        ['Nombre', 'Edad', 'Ciudad'],
        ['John', 30, 'New York'],
        ['Emily', 28, 'Los Angeles']
    ]
    
    with open('datos.csv', 'w', newline='') as archivo_csv:
        escritor_csv = csv.writer(archivo_csv)
        for fila in datos:
            escritor_csv.writerow(fila)
    ```

### Parámetros Adicionales

- **newline**: Controla el carácter de nueva línea en la escritura de archivos CSV.
- **quoting**: Define cómo se deben manejar los campos con caracteres especiales durante la escritura.

### Funcionalidades Avanzadas

- **csv.DictReader()**
  - Lee un archivo CSV como un diccionario ordenado por filas
  - Sintaxis: `csv.DictReader(archivo, fieldnames=None)`
    - `archivo`: Objeto de archivo abierto o iterable de líneas CSV
    - `fieldnames`: Nombres de campo si no están en la primera fila
  - Ejemplo:
    ```python
    with open('datos.csv', 'r') as archivo_csv:
        lector_dict_csv = csv.DictReader(archivo_csv)
        for fila in lector_dict_csv:
            print(fila['Nombre'], fila['Edad'], fila['Ciudad'])
    ```

- **csv.DictWriter()**
  - Escribe filas en un archivo CSV usando diccionarios como entrada
  - Sintaxis: `csv.DictWriter(archivo, fieldnames, delimiter=',')`
    - `archivo`: Objeto de archivo abierto para escribir
    - `fieldnames`: Lista de nombres de campo
    - `delimiter`: Carácter delimitador de campos (por defecto `,`)
  - Ejemplo:
    ```python
    datos = [
        {'Nombre': 'John', 'Edad': 30, 'Ciudad': 'New York'},
        {'Nombre': 'Emily', 'Edad': 28, 'Ciudad': 'Los Angeles'}
    ]
    
    with open('datos.csv', 'w', newline='') as archivo_csv:
        nombres_campos = ['Nombre', 'Edad', 'Ciudad']
        escritor_dict_csv = csv.DictWriter(archivo_csv, fieldnames=nombres_campos)
        escritor_dict_csv.writeheader()
        for fila in datos:
            escritor_dict_csv.writerow(fila)
    ```

### Resumen
El módulo `csv` en Python facilita la lectura y escritura de archivos CSV, un formato comúnmente utilizado para almacenar datos tabulares. Ofrece funciones básicas y avanzadas para manipular archivos CSV de manera eficiente, adaptándose a diferentes necesidades como la lectura secuencial, la escritura de filas y el manejo de datos estructurados como diccionarios.
