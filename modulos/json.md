
# Mapa Mental Completo: Módulo `json` en Python

## json
- Formato de intercambio de datos ligero
- Serialización y deserialización de datos estructurados

### Funciones Principales

#### Serialización (Python a JSON)

- **json.dumps()**
  - Convierte objetos Python a una cadena JSON
  - Sintaxis: `json.dumps(objeto, indent=None)`
    - `objeto`: Objeto Python a serializar
    - `indent`: Nivel de sangrado para la salida (opcional)
  - Ejemplo:
    ```python
    import json
    
    datos = {'nombre': 'John', 'edad': 30, 'ciudad': 'New York'}
    json_data = json.dumps(datos, indent=2)
    print(json_data)
    ```
  
- **json.dump()**
  - Escribe objetos Python serializados a un archivo JSON
  - Sintaxis: `json.dump(objeto, archivo, indent=None)`
    - `objeto`: Objeto Python a serializar
    - `archivo`: Archivo donde se escribirá la salida JSON
    - `indent`: Nivel de sangrado para la salida (opcional)
  - Ejemplo:
    ```python
    with open('datos.json', 'w') as archivo:
        json.dump(datos, archivo, indent=2)
    ```

#### Deserialización (JSON a Python)

- **json.loads()**
  - Convierte una cadena JSON en un objeto Python
  - Sintaxis: `json.loads(cadena)`
    - `cadena`: Cadena JSON a deserializar
  - Ejemplo:
    ```python
    json_string = '{"nombre": "John", "edad": 30, "ciudad": "New York"}'
    datos = json.loads(json_string)
    print(datos['nombre'])
    ```

- **json.load()**
  - Lee y deserializa un archivo JSON en un objeto Python
  - Sintaxis: `json.load(archivo)`
    - `archivo`: Archivo JSON a leer y deserializar
  - Ejemplo:
    ```python
    with open('datos.json', 'r') as archivo:
        datos = json.load(archivo)
    print(datos['ciudad'])
    ```

### Formato JSON

- **Objeto JSON**
  - Conjunto no ordenado de pares clave-valor
  - Claves deben ser cadenas
  - Valores pueden ser tipos de datos JSON válidos (números, cadenas, booleanos, listas, objetos anidados, `null`)

### Funciones Adicionales

- **json.dumps() con parámetros opcionales**
  - `skipkeys`: Omite claves no serializables en los diccionarios (por defecto `False`)
  - `ensure_ascii`: Garantiza que todos los caracteres estén codificados en ASCII (por defecto `True`)
  - `sort_keys`: Ordena las claves del diccionario en la salida JSON (por defecto `False`)

### Ejemplo de Uso Completo

```python
import json

# Serializar un diccionario a JSON y escribirlo en un archivo
datos = {'nombre': 'John', 'edad': 30, 'ciudad': 'New York'}
with open('datos.json', 'w') as archivo:
    json.dump(datos, archivo, indent=2)

# Leer y deserializar un archivo JSON
with open('datos.json', 'r') as archivo:
    datos_cargados = json.load(archivo)
    print(datos_cargados['nombre'])
