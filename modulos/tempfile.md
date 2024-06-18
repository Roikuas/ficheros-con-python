
# Mapa Mental Completo: Módulo `tempfile` en Python

## tempfile
- Creación y manejo de archivos y directorios temporales
- Manejo automático de la limpieza de archivos temporales

### Funciones Principales

#### Archivos Temporales
- **NamedTemporaryFile()**
  - Crea un archivo temporal con nombre
  - Sintaxis: `tempfile.NamedTemporaryFile()`
  - Parámetros:
    - `mode`: Modo de apertura del archivo (por defecto `'w+b'`)
    - `delete`: Elimina el archivo al cerrarlo (por defecto `True`)

- **TemporaryFile()**
  - Crea un archivo temporal sin nombre
  - Sintaxis: `tempfile.TemporaryFile()`
  - Parámetros:
    - `mode`: Modo de apertura del archivo (por defecto `'w+b'`)

#### Directorios Temporales
- **TemporaryDirectory()**
  - Crea un directorio temporal
  - Sintaxis: `tempfile.TemporaryDirectory()`
  - Parámetros:
    - `suffix`: Sufijo del nombre del directorio
    - `prefix`: Prefijo del nombre del directorio
    - `dir`: Directorio donde se crea el directorio temporal

### Funciones de Bajo Nivel
- **mkstemp()**
  - Crea un archivo temporal y devuelve un descriptor de archivo y la ruta
  - Sintaxis: `tempfile.mkstemp()`
  - Parámetros:
    - `suffix`: Sufijo del nombre del archivo
    - `prefix`: Prefijo del nombre del archivo
    - `dir`: Directorio donde se crea el archivo temporal
    - `text`: Abre el archivo en modo texto si es `True`

- **mkdtemp()**
  - Crea un directorio temporal y devuelve la ruta
  - Sintaxis: `tempfile.mkdtemp()`
  - Parámetros:
    - `suffix`: Sufijo del nombre del directorio
    - `prefix`: Prefijo del nombre del directorio
    - `dir`: Directorio donde se crea el directorio temporal

- **gettempdir()**
  - Devuelve la ruta del directorio temporal predeterminado
  - Sintaxis: `tempfile.gettempdir()`

- **gettempdirb()**
  - Devuelve la ruta del directorio temporal predeterminado como bytes
  - Sintaxis: `tempfile.gettempdirb()`

### Ejemplo de Código

```python
import tempfile
import os

# Crear un archivo temporal con nombre
with tempfile.NamedTemporaryFile(delete=False) as temp_file:
    print(f"Archivo temporal: {temp_file.name}")
    temp_file.write(b"Hola, mundo!")

# Leer el archivo temporal
with open(temp_file.name, 'r') as file:
    contenido = file.read()
    print(f"Contenido del archivo temporal: {contenido}")

# Crear un archivo temporal sin nombre
with tempfile.TemporaryFile() as temp_file:
    temp_file.write(b"Hola, mundo!")
    temp_file.seek(0)
    contenido = temp_file.read()
    print(f"Contenido del archivo temporal sin nombre: {contenido}")

# Crear un directorio temporal
with tempfile.TemporaryDirectory() as temp_dir:
    print(f"Directorio temporal: {temp_dir}")
    # Crear un archivo dentro del directorio temporal
    temp_file_path = os.path.join(temp_dir, "temp_file.txt")
    with open(temp_file_path, 'w') as temp_file:
        temp_file.write("Hola, mundo!")
    # Leer el archivo dentro del directorio temporal
    with open(temp_file_path, 'r') as temp_file:
        contenido = temp_file.read()
        print(f"Contenido del archivo en el directorio temporal: {contenido}")

# Usar mkstemp para crear un archivo temporal
fd, path = tempfile.mkstemp()
with os.fdopen(fd, 'w') as temp_file:
    temp_file.write("Hola, mundo!")
print(f"Archivo temporal creado con mkstemp: {path}")

# Usar mkdtemp para crear un directorio temporal
temp_dir = tempfile.mkdtemp()
print(f"Directorio temporal creado con mkdtemp: {temp_dir}")

# Obtener el directorio temporal predeterminado
temp_dir_default = tempfile.gettempdir()
print(f"Directorio temporal predeterminado: {temp_dir_default}")
