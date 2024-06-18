
# Mapa Mental Completo: Módulo `shutil` en Python

## shutil
- Operaciones de alto nivel en archivos y colecciones de archivos
- Copiar y eliminar archivos y directorios

### Operaciones de Copia
- **shutil.copy()**
  - Copia contenido de un archivo a otro
  - Sintaxis: `shutil.copy(src, dst)`
- **shutil.copy2()**
  - Copia contenido de un archivo a otro preservando metadatos
  - Sintaxis: `shutil.copy2(src, dst)`
- **shutil.copyfile()**
  - Copia solo el contenido de un archivo
  - Sintaxis: `shutil.copyfile(src, dst)`
- **shutil.copytree()**
  - Copia recursivamente un directorio y su contenido
  - Sintaxis: `shutil.copytree(src, dst)`

### Operaciones de Movimiento
- **shutil.move()**
  - Mueve un archivo o directorio a una nueva ubicación
  - Sintaxis: `shutil.move(src, dst)`

### Operaciones de Eliminación
- **shutil.rmtree()**
  - Elimina recursivamente un directorio y su contenido
  - Sintaxis: `shutil.rmtree(path)`

### Manipulación de Archivos Comprimidos
- **shutil.make_archive()**
  - Crea un archivo comprimido (zip, tar, etc.) a partir de un directorio
  - Sintaxis: `shutil.make_archive(base_name, format, root_dir)`
- **shutil.unpack_archive()**
  - Extrae un archivo comprimido en un directorio
  - Sintaxis: `shutil.unpack_archive(filename, extract_dir)`

### Gestión del Uso de Disco
- **shutil.disk_usage()**
  - Devuelve el uso del disco en una ruta específica
  - Sintaxis: `shutil.disk_usage(path)`

### Permisos
- **shutil.chown()**
  - Cambia el propietario y grupo de un archivo o directorio
  - Sintaxis: `shutil.chown(path, user, group)`

### Ejemplo de Código

```python
import shutil
import os

# Copiar archivo
shutil.copy('archivo_origen.txt', 'archivo_destino.txt')

# Copiar archivo con metadatos
shutil.copy2('archivo_origen.txt', 'archivo_destino.txt')

# Copiar solo contenido de archivo
shutil.copyfile('archivo_origen.txt', 'archivo_destino.txt')

# Copiar directorio recursivamente
shutil.copytree('directorio_origen', 'directorio_destino')

# Mover archivo o directorio
shutil.move('ruta_origen', 'ruta_destino')

# Eliminar directorio recursivamente
shutil.rmtree('directorio_a_eliminar')

# Crear archivo comprimido
shutil.make_archive('archivo_comprimido', 'zip', 'directorio_a_comprimir')

# Extraer archivo comprimido
shutil.unpack_archive('archivo_comprimido.zip', 'directorio_de_destino')

# Obtener uso de disco
uso_disco = shutil.disk_usage('/')
print(f'Total: {uso_disco.total}, Usado: {uso_disco.used}, Libre: {uso_disco.free}')

# Cambiar propietario y grupo
shutil.chown('archivo.txt', user='nuevo_usuario', group='nuevo_grupo')
