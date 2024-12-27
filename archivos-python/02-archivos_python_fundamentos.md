# Fundamentos del Manejo de Archivos con Python

El manejo de archivos en Python es una habilidad esencial para trabajar con datos almacenados en archivos. Python proporciona una interfaz sencilla para abrir, leer, escribir y cerrar archivos utilizando su biblioteca estándar. A continuación, se explican los conceptos fundamentales de manera detallada y clara.

---

## Índice

1. [Abrir un Archivo](#abrir-un-archivo)
2. [Leer un Archivo](#leer-un-archivo)
3. [Escribir en un Archivo](#escribir-en-un-archivo)
4. [Cerrar un Archivo](#cerrar-un-archivo)
5. [Uso del Bloque `with`](#uso-del-bloque-with)
6. [Manejo de Errores](#manejo-de-errores)
7. [Manipulación Avanzada](#manipulación-avanzada)
   - [Archivos Binarios](#archivos-binarios)
   - [Módulo `os`](#módulo-os)
   - [Módulo `shutil`](#módulo-shutil)
   - [Trabajando con Punteros](#trabajando-con-punteros)
8. [Resumen](#resumen)

---

## Abrir un Archivo

Abrir un archivo es el primer paso para trabajar con su contenido. La función `open()` se utiliza para este propósito.

### Sintaxis de `open()`

```python
open(file, mode='r', encoding=None)
```

- **file**: Especifica la ruta del archivo. Puede ser relativa (respecto al directorio actual) o absoluta.
- **mode**: Define cómo interactuar con el archivo (lectura, escritura, etc.). Por defecto, es `'r'` (lectura).
- **encoding**: Especifica la codificación del archivo. Recomendado para texto multilingüe (e.g., `'utf-8'`).

### Modos de Apertura

- `'r'`: Lectura. Lanza un error si el archivo no existe.
- `'w'`: Escritura. Crea el archivo si no existe o sobreescribe su contenido.
- `'a'`: Agregar. Crea el archivo si no existe y agrega contenido al final.
- `'b'`: Binario. Se utiliza junto con otros modos para manejar archivos no textuales (e.g., imágenes).
- `'x'`: Creación exclusiva. Falla si el archivo ya existe.
- `'r+'`: Lectura y escritura. El archivo debe existir previamente.
- `'w+'`: Escritura y lectura. Sobrescribe el archivo si existe.
- `'a+'`: Agregar y lectura. Crea el archivo si no existe.

### Ejemplo de Apertura

```python
# Abrir un archivo en modo lectura
archivo = open("archivo.txt", "r")
```

---

## Leer un Archivo

La lectura de un archivo permite obtener su contenido. Existen varios métodos disponibles según la necesidad.

### Métodos de Lectura

- **`read(size=-1)`**: Lee el contenido completo como una cadena. Si se proporciona `size`, lee hasta esa cantidad de caracteres.
- **`readline()`**: Lee una línea completa del archivo.
- **`readlines()`**: Devuelve una lista de todas las líneas del archivo.

### Ejemplo

```python
# Leer todo el contenido
archivo = open("archivo.txt", "r")
contenido = archivo.read()
print(contenido)
archivo.close()

# Leer línea por línea
archivo = open("archivo.txt", "r")
for linea in archivo:
    print(linea.strip())
archivo.close()
```

---

## Escribir en un Archivo

Escribir en archivos permite guardar datos en disco. Es importante elegir el modo adecuado para no perder datos importantes.

### Métodos de Escritura

- **`write(string)`**: Escribe una cadena en el archivo.
- **`writelines(lines)`**: Escribe una lista de cadenas al archivo. No agrega saltos de línea automáticamente.

### Ejemplo

```python
# Sobrescribir contenido
archivo = open("archivo.txt", "w")
archivo.write("Hola, mundo!\n")
archivo.writelines(["Línea 1\n", "Línea 2\n"])
archivo.close()
```

---

## Cerrar un Archivo

Cerrar un archivo es esencial para liberar los recursos del sistema. Esto se realiza utilizando el método `close()`.

### Ejemplo

```python
archivo = open("archivo.txt", "r")
contenido = archivo.read()
archivo.close()
```

---

## Uso del Bloque `with`

El bloque `with` garantiza que el archivo se cierre correctamente, incluso si ocurre un error durante su manipulación.

### Ejemplo

```python
with open("archivo.txt", "r") as archivo:
    contenido = archivo.read()
    print(contenido)
# El archivo se cierra automáticamente
```

---

## Manejo de Errores

Gestionar errores previene fallos inesperados durante el manejo de archivos.

### Errores Comunes

- **`FileNotFoundError`**: Ocurre si el archivo no existe.
- **`PermissionError`**: Se lanza si no se tienen permisos.
- **`IOError`**: Problemas generales de entrada/salida.

### Ejemplo

```python
try:
    with open("archivo_no_existente.txt", "r") as archivo:
        contenido = archivo.read()
except FileNotFoundError:
    print("El archivo no existe.")
except PermissionError:
    print("No tienes permisos para acceder al archivo.")
except IOError:
    print("Ocurrió un error al manejar el archivo.")
```

---

## Manipulación Avanzada

Python ofrece herramientas avanzadas para operaciones específicas con archivos.

### Archivos Binarios

Se utilizan para datos no textuales, como imágenes o videos.

```python
with open("imagen.jpg", "rb") as archivo:
    contenido = archivo.read()
```

### Módulo `os`

Ofrece funciones para gestionar archivos y directorios.

```python
import os
os.remove("archivo.txt")  # Eliminar un archivo
```

### Módulo `shutil`

Facilita operaciones como copiar y mover archivos.

```python
import shutil
shutil.copy("archivo.txt", "copia_archivo.txt")  # Copiar archivo
```

### Trabajando con Punteros

El puntero del archivo indica la posición actual para lectura/escritura.

- **`tell()`**: Retorna la posición actual del puntero.
- **`seek(offset, whence=0)`**: Cambia la posición del puntero.
  - `offset`: Número de bytes a desplazar.
  - `whence`: Referencia (0: inicio, 1: posición actual, 2: final).

#### Ejemplo

```python
with open("archivo.txt", "r") as archivo:
    print(archivo.tell())  # Posición inicial
    archivo.seek(5)        # Desplazar al quinto byte
    print(archivo.read())
```

---

## Resumen

El manejo de archivos en Python es una habilidad esencial para cualquier programador. Desde operaciones básicas como abrir y leer archivos hasta tareas avanzadas como manipulación binaria y control de punteros, estas herramientas permiten trabajar de forma segura y eficiente con datos almacenados.

---
