
# Mapa Mental Completo: Módulo `pathlib` en Python

## pathlib
- Manipulación de rutas de archivos y directorios
- Interfaz orientada a objetos

### Clases Principales
- **Path**
  - Clase base para operaciones de rutas
  - Compatible con sistemas operativos
- **PurePath**
  - Manipulación de rutas sin operaciones de E/S
  - Clases derivadas: `PurePosixPath`, `PureWindowsPath`

### Creación de Objetos Path
- **Path()**
  - Crea un objeto Path
  - Sintaxis: `Path('ruta/al/archivo')`
- **PurePath()**
  - Crea un objeto PurePath
  - Sintaxis: `PurePath('ruta/al/archivo')`

### Propiedades y Métodos Comunes
- **name**
  - Nombre del archivo o directorio
- **parent**
  - Directorio padre
- **stem**
  - Nombre del archivo sin la extensión
- **suffix**
  - Extensión del archivo
- **parts**
  - Partes de la ruta como una tupla
- **exists()**
  - Verifica si la ruta existe
- **is_file()**
  - Verifica si la ruta es un archivo
- **is_dir()**
  - Verifica si la ruta es un directorio
- **iterdir()**
  - Itera sobre los elementos en un directorio

### Operaciones de Archivos
- **read_text()**
  - Lee el contenido de un archivo de texto
- **read_bytes()**
  - Lee el contenido de un archivo como bytes
- **write_text()**
  - Escribe texto en un archivo
- **write_bytes()**
  - Escribe bytes en un archivo
- **open()**
  - Abre un archivo
- **unlink()**
  - Elimina un archivo

### Operaciones de Directorios
- **mkdir()**
  - Crea un directorio
- **rmdir()**
  - Elimina un directorio vacío
- **rename()**
  - Renombra un archivo o directorio
- **replace()**
  - Reemplaza un archivo o directorio

### Manipulación de Rutas
- **joinpath()**
  - Une componentes de ruta
- **relative_to()**
  - Calcula la ruta relativa a otra
- **with_name()**
  - Devuelve una nueva ruta con un nombre diferente
- **with_suffix()**
  - Devuelve una nueva ruta con una extensión diferente
- **resolve()**
  - Devuelve la ruta absoluta

### Uso de Globs
- **glob()**
  - Encuentra todas las rutas que coinciden con un patrón
- **rglob()**
  - Encuentra todas las rutas recursivamente que coinciden con un patrón

### Ejemplo de Código

```python
from pathlib import Path

# Crear objeto Path
ruta = Path('archivo.txt')

# Verificar si el archivo existe
if ruta.exists():
    print("El archivo existe")

# Leer contenido de un archivo de texto
contenido = ruta.read_text()
print(contenido)

# Escribir texto en un archivo
ruta.write_text('Nuevo contenido')

# Crear un nuevo directorio
nuevo_directorio = Path('nuevo_directorio')
nuevo_directorio.mkdir(exist_ok=True)

# Listar archivos en un directorio
for archivo in nuevo_directorio.iterdir():
    print(archivo)

# Renombrar un archivo
ruta.rename('archivo_renombrado.txt')

# Eliminar un archivo
ruta.unlink()
