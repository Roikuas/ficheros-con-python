# Mapa Mental: Módulo `os` en Python

## os
- Interacción con el sistema operativo
- Manipulación de archivos y directorios

### Operaciones de Archivos
- **os.open()**
  - Abre un archivo con modos de apertura específicos
- **os.read()**
  - Lee contenido de un archivo abierto
- **os.write()**
  - Escribe contenido en un archivo abierto
- **os.close()**
  - Cierra un archivo abierto
- **os.remove()**
  - Elimina un archivo
- **os.rename()**
  - Renombra un archivo

### Operaciones de Directorios
- **os.getcwd()**
  - Obtiene el directorio de trabajo actual
- **os.chdir()**
  - Cambia el directorio de trabajo actual
- **os.listdir()**
  - Lista archivos y directorios en un directorio
- **os.mkdir()**
  - Crea un nuevo directorio
- **os.makedirs()**
  - Crea un directorio y todos sus directorios padres necesarios
- **os.rmdir()**
  - Elimina un directorio vacío
- **os.removedirs()**
  - Elimina un directorio y sus directorios padres vacíos

### Manipulación de Rutas
- **os.path.join()**
  - Une componentes de ruta
- **os.path.exists()**
  - Verifica si una ruta existe
- **os.path.isfile()**
  - Verifica si una ruta es un archivo
- **os.path.isdir()**
  - Verifica si una ruta es un directorio
- **os.path.abspath()**
  - Obtiene la ruta absoluta
- **os.path.basename()**
  - Obtiene el nombre de archivo desde una ruta
- **os.path.dirname()**
  - Obtiene el nombre del directorio desde una ruta
- **os.path.split()**
  - Divide una ruta en directorio y nombre de archivo

### Información de Ficheros
- **os.stat()**
  - Obtiene información detallada de un archivo
- **os.lstat()**
  - Obtiene información detallada de un archivo sin seguir enlaces simbólicos
- **os.path.getsize()**
  - Obtiene el tamaño de un archivo
- **os.path.getmtime()**
  - Obtiene la última fecha de modificación de un archivo
- **os.path.getatime()**
  - Obtiene la última fecha de acceso de un archivo
- **os.path.getctime()**
  - Obtiene la fecha de creación de un archivo

### Permisos y Propiedades
- **os.chmod()**
  - Cambia permisos de un archivo o directorio
- **os.chown()**
  - Cambia el propietario y grupo de un archivo o directorio
- **os.umask()**
  - Establece la máscara de creación de archivos

### Manejo de Procesos
- **os.system()**
  - Ejecuta comandos del sistema operativo
- **os.popen()**
  - Abre una tubería a o desde el comando del sistema operativo
- **os.exec()**
  - Reemplaza el proceso actual con un nuevo proceso

### Variables de Entorno
- **os.environ**
  - Acceso a variables de entorno
- **os.getenv()**
  - Obtiene el valor de una variable de entorno
- **os.putenv()**
  - Establece una variable de entorno
- **os.unsetenv()**
  - Elimina una variable de entorno

## Ejemplo de Código

```python
import os

# Obtener directorio de trabajo actual
cwd = os.getcwd()
print("Directorio actual:", cwd)

# Listar archivos en el directorio actual
files = os.listdir(cwd)
print("Archivos en el directorio actual:", files)

# Crear un nuevo directorio
os.mkdir("nuevo_directorio")

# Renombrar el directorio
os.rename("nuevo_directorio", "directorio_renombrado")

# Eliminar el directorio
os.rmdir("directorio_renombrado")

# Verificar si un archivo existe
file_exists = os.path.exists("archivo.txt")
print("¿El archivo existe?", file_exists)

# Obtener información detallada del archivo
if file_exists:
    info = os.stat("archivo.txt")
    print("Información del archivo:", info)

# Cambiar permisos de un archivo
os.chmod("archivo.txt", 0o644)
