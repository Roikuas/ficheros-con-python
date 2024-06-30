# Mapa Mental: Manejo de Archivos en Python

## 📜 Operaciones Básicas
- **Abrir un Archivo**: `open(nombre_archivo, modo)`
- **Modos de Apertura**:
  - `r`: Lectura
  - `w`: Escritura (sobrescribe el archivo)
  - `a`: Añadir al final
  - `x`: Crear archivo y escribir (falla si el archivo ya existe)
  - `b`: Modo binario
  - `t`: Modo texto (predeterminado)
  - `+`: Lectura y escritura

## ✍ Lectura de Archivos
- `read(size)`: Leer un tamaño específico de caracteres
- `readline()`: Leer una línea
- `readlines()`: Leer todas las líneas como una lista
- Iterar sobre el archivo.

## ✍ Escribir en un fichero
- `write(cadena)`:  escribir en un archivo.
- `writelines(lista_cadenas)`: escribir una lista de líneas en un archivo.

## ✍ Cerrar un fichero
- `close()`: Cierra el fichero manualmente (no necesario con `with open`).

## Mas
- `append()` :Añadir contenido a Un archivo existente:
-  `seek()` : Mover el puntero de lectura/escritura en un archivo.
- `stat()`: Obtener información sobre el archivo:
-  `remove()` : Eliminar Un archivo:
-  `rename()` : Renombrar Un archivo:
-  `exists()` : Verificar si Un archivo existe:
- `tell()`: Para obtener la posición actual del puntero en el archivo.
- `flush()`: Vacía el buffer de escritura.
- `read()`: Lee una cantidad específica de bytes o todo el archivo.

## Manejo de directorios
- `mkdir()` :  Crear un directorio.
-  `rmdir()` : Eliminar Un directorio vacío.
- `rmtree()`:  Eliminar un directorio y su contenido.
- `listdir()` : Listar los archivos y directorios en una ubicación.
- `walk()`  :  Navegar por la estructura de directorios.

## Copiar y mover archivos/directorios
- `copy()` : Copiar Un archivo.
- `move()` : Mover Un archivo.
- `copytree()` : Copiar Un directorio y su contenido.
- `move()` : Mover Un directorio y su contenido.

## Rutas y nombres de archivos

- `getcwd()` : Obtener la ruta actual: 
- `chdir()` : Cambiar eI directorio de trabajo:
- `abspath()` :  Obtener la ruta absoluta de Un archivo:
- `join()` : Unir rutas y nombres de archivo: 
- `split()` : Separar una ruta y un nombre de archivo:
- `splitext()` : Obtener la extensión de Un archivo:
- `isabs()` : Verificar si una ruta es absoluta:
- `isdir()` : Verificar si Una ruta es Un directorio:
- `exists()` : Verificar si una ruta existe: 

