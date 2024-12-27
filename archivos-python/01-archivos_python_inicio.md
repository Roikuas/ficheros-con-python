# Fundamentos del Manejo de Archivos en Python: Guía Completa

## Índice

1. [Conceptos Básicos de Archivos](#1-conceptos-básicos-de-archivos)

   - [¿Qué es un archivo?](#qué-es-un-archivo)
   - [Tipos de Archivos](#tipos-de-archivos)

2. [Apertura de Archivos en Profundidad](#2-apertura-de-archivos-en-profundidad)

   - [La Función open()](#la-función-open)
   - [Parámetros Detallados](#parámetros-detallados)
   - [Modos de Apertura Explicados](#modos-de-apertura-explicados)

3. [Operaciones de Lectura en Detalle](#3-operaciones-de-lectura-en-detalle)

   - [Métodos de Lectura](#métodos-de-lectura)
   - [read()](#read)
   - [readline()](#readline)
   - [readlines()](#readlines)

4. [Operaciones de Escritura Detalladas](#4-operaciones-de-escritura-detalladas)

   - [Métodos de Escritura](#métodos-de-escritura)
   - [write()](#write)
   - [writelines()](#writelines)

5. [Control del Puntero de Archivo](#5-control-del-puntero-de-archivo)

   - [Métodos de Posicionamiento](#métodos-de-posicionamiento)
   - [tell()](#tell)
   - [seek()](#seek)

6. [Manejo de Errores y Excepciones](#6-manejo-de-errores-y-excepciones)

   - [Excepciones Comunes](#excepciones-comunes)

7. [Buffers y Rendimiento](#7-buffers-y-rendimiento)

   - [Control de Buffer](#control-de-buffer)

8. [Codificación de Caracteres](#8-codificación-de-caracteres)

   - [Manejo de Encodings](#manejo-de-encodings)

9. [Ejemplos Prácticos Avanzados](#9-ejemplos-prácticos-avanzados)

   - [Procesamiento de Archivo Línea por Línea](#procesamiento-de-archivo-línea-por-línea)
   - [Copia de Archivos con Buffer](#copia-de-archivos-con-buffer)

10. [Buenas Prácticas y Recomendaciones](#10-buenas-prácticas-y-recomendaciones)

## 1. Conceptos Básicos de Archivos

### ¿Qué es un archivo?

Un archivo es una colección secuencial de datos almacenados en un dispositivo de almacenamiento. En Python, los archivos son objetos que proporcionan una interfaz para interactuar con archivos en el sistema operativo.

#### Elementos Fundamentales

```Python
# Estructura básica de un path
from pathlib import Path
ruta = Path('/home/usuario/documentos/archivo.txt')

# Componentes de la ruta
print(ruta.parent)  # Directorio padre
print(ruta.name)    # Nombre del archivo
print(ruta.suffix)  # Extensión
print(ruta.stem)    # Nombre sin extensión
```

#### Características Esenciales

- **Persistencia**: Los datos sobreviven al cierre del programa
- **Organización jerárquica**: Sistema de directorios y subdirectorios
- **Acceso aleatorio**: Capacidad de acceder a cualquier parte del archivo
- **Atomicidad**: Garantías sobre operaciones indivisibles

### Tipos de Archivos

1. **Archivos de Texto**

   - Contienen caracteres legibles por humanos
   - Se codifican usando ASCII, UTF-8, etc.
   - Ejemplos: .txt, .csv, .py, .html

2. **Archivos Binarios**
   - Contienen datos en formato binario
   - No son directamente legibles por humanos
   - Ejemplos: imágenes, archivos ejecutables, archivos comprimidos

## 2. Apertura de Archivos en Profundidad

### La Función `open()`

```python
archivo = open(nombre_archivo, modo, buffering, encoding, errors, newline, closefd, opener)
```

#### Parámetros Detallados:

- `nombre_archivo`: Ruta al archivo (absoluta o relativa)
- `modo`: Especifica el modo de operación
- `buffering`: Controla el buffer (-1, 0, o >0)
- `encoding`: Especifica la codificación del texto
- `errors`: Cómo manejar errores de codificación
- `newline`: Cómo manejar los saltos de línea
- `closefd`: Si se debe cerrar el descriptor de archivo
- `opener`: Un opener personalizado opcional

### Modos de Apertura Explicados

- `'r'`: Lectura (por defecto)
- `'w'`: Escritura (sobrescribe el archivo)
- `'a'`: Append (añade al final del archivo)
- `'x'`: Creación exclusiva
- `'b'`: Modo binario
- `'t'`: Modo texto (por defecto)
- `'+'`: Lectura y escritura

#### Uso del Contexto `with`

La mejor práctica es usar el administrador de contexto `with`:

```python
with open('archivo.txt', 'r') as archivo:
    contenido = archivo.read()
```

Esto garantiza que el archivo se cierre automáticamente.

#### 3.1 Modos Básicos de Apertura

##### Modo 'r' (Lectura)

```python
# Solo lectura
with open('archivo.txt', 'r') as f:
    contenido = f.read()
# - El archivo debe existir
# - Puntero al inicio
# - Solo operaciones de lectura
```

##### Modo 'w' (Escritura)

```python
# Escritura (crea nuevo o sobrescribe)
with open('archivo.txt', 'w') as f:
    f.write('Nuevo contenido')
# - Crea archivo si no existe
# - Sobrescribe si existe
# - Puntero al inicio
```

##### Modo 'a' (Append)

```python
# Añadir al final
with open('archivo.txt', 'a') as f:
    f.write('Contenido adicional')
# - Crea archivo si no existe
# - Puntero al final
# - Solo escritura al final
```

##### Modo 'x' (Creación Exclusiva)

```python
# Crear archivo nuevo
try:
    with open('archivo.txt', 'x') as f:
        f.write('Contenido inicial')
except FileExistsError:
    print("El archivo ya existe")
# - Error si el archivo existe
# - Crea nuevo archivo
# - Modo escritura
```

#### 3.2 Modos Combinados

##### Modo 'r+' (Lectura y Escritura)

```python
# Lectura y escritura
with open('archivo.txt', 'r+') as f:
    contenido = f.read()
    f.write('Nuevo contenido')
# - Archivo debe existir
# - Puntero al inicio
# - Permite lectura y escritura
# - No sobrescribe automáticamente
```

##### Modo 'w+' (Escritura y Lectura)

```python
# Escritura y lectura
with open('archivo.txt', 'w+') as f:
    f.write('Contenido nuevo')
    f.seek(0)  # Volver al inicio
    contenido = f.read()
# - Crea archivo o sobrescribe
# - Puntero al inicio
# - Permite escritura y lectura
```

##### Modo 'a+' (Append y Lectura)

```python
# Append y lectura
with open('archivo.txt', 'a+') as f:
    f.write('Nuevo contenido')
    f.seek(0)  # Volver al inicio para leer
    contenido = f.read()
# - Crea archivo si no existe
# - Puntero al final
# - Permite append y lectura
```

#### 3.3 Modificadores de Modo

##### Modificador 'b' (Modo Binario)

```python
# Modo binario
with open('archivo.bin', 'rb') as f:
    datos = f.read()

with open('archivo.bin', 'wb') as f:
    f.write(bytes([65, 66, 67]))
```

##### Modificador 't' (Modo Texto)

```python
# Modo texto (default)
with open('archivo.txt', 'rt') as f:
    texto = f.read()
```

## 3. Operaciones de Lectura en Detalle

### Métodos de Lectura

1. **read()**

   ```python
   with open('archivo.txt', 'r') as f:
       # Lee todo el archivo
       contenido = f.read()

       # Lee n caracteres
       primeros_10 = f.read(10)
   ```

2. **readline()**

   ```python
   with open('archivo.txt', 'r') as f:
       # Lee una línea
       primera_linea = f.readline()

       # Lee una línea con límite de caracteres
       parte_linea = f.readline(5)
   ```

3. **readlines()**

   ```python
   with open('archivo.txt', 'r') as f:
       # Lee todas las líneas en una lista
       lineas = f.readlines()

       # Lee n líneas
       algunas_lineas = f.readlines(100)
   ```

## 4. Operaciones de Escritura Detalladas

### Métodos de Escritura

1. **write()**

   ```python
   with open('archivo.txt', 'w') as f:
       # Escribe una cadena
       f.write('Hola mundo\n')

       # Escribe múltiples cadenas
       f.write('Línea 1\n')
       f.write('Línea 2\n')
   ```

2. **writelines()**
   ```python
   with open('archivo.txt', 'w') as f:
       lineas = ['Línea 1\n', 'Línea 2\n', 'Línea 3\n']
       f.writelines(lineas)
   ```

## 5. Control del Puntero de Archivo

### Métodos de Posicionamiento

1. **tell()**

   ```python
   with open('archivo.txt', 'r') as f:
       # Obtiene la posición actual del puntero
       posicion = f.tell()
   ```

2. **seek()**
   ```python
   with open('archivo.txt', 'r') as f:
       # Mueve el puntero a una posición específica
       f.seek(0)  # Inicio del archivo
       f.seek(10)  # 10 bytes desde el inicio
       f.seek(0, 2)  # Final del archivo
   ```

## 6. Manejo de Errores y Excepciones

### Excepciones Comunes

```python
try:
    with open('archivo.txt', 'r') as f:
        contenido = f.read()
except FileNotFoundError:
    print("El archivo no existe")
except PermissionError:
    print("Sin permisos para acceder al archivo")
except IOError:
    print("Error de E/S")
except UnicodeDecodeError:
    print("Error de decodificación")
finally:
    print("Operación finalizada")
```

## 7. Buffers y Rendimiento

### Control de Buffer

```python
# Sin buffer
with open('archivo.txt', 'w', buffering=0) as f:
    f.write('Datos')

# Buffer por línea
with open('archivo.txt', 'w', buffering=1) as f:
    f.write('Datos\n')

# Buffer con tamaño específico
with open('archivo.txt', 'w', buffering=4096) as f:
    f.write('Datos')
```

## 8. Codificación de Caracteres

### Manejo de Encodings

```python
# Lectura con encoding específico
with open('archivo.txt', 'r', encoding='utf-8') as f:
    contenido = f.read()

# Escritura con encoding específico
with open('archivo.txt', 'w', encoding='utf-8', errors='ignore') as f:
    f.write('Texto con caracteres especiales: áéíóú')
```

## 9. Ejemplos Prácticos Avanzados

### Procesamiento de Archivo Línea por Línea

```python
def procesar_archivo_grande(nombre_archivo):
    with open(nombre_archivo, 'r') as f:
        for num_linea, linea in enumerate(f, 1):
            # Procesa cada línea eficientemente
            linea = linea.strip()
            if linea:
                print(f"Línea {num_linea}: {linea}")

# Uso
procesar_archivo_grande('archivo_grande.txt')
```

### Copia de Archivos con Buffer

```python
def copiar_archivo(origen, destino, tamano_buffer=4096):
    with open(origen, 'rb') as f_origen:
        with open(destino, 'wb') as f_destino:
            while True:
                datos = f_origen.read(tamano_buffer)
                if not datos:
                    break
                f_destino.write(datos)

# Uso
copiar_archivo('original.txt', 'copia.txt')
```

### Manipulación de Rutas

Python proporciona el módulo `os.path` y `pathlib` para manejar rutas de archivos:

```python
from pathlib import Path

# Crear objeto Path
ruta = Path('carpeta/subcarpeta/archivo.txt')

# Verificar si existe
if ruta.exists():
    print('El archivo existe')

# Crear directorios
ruta.parent.mkdir(parents=True, exist_ok=True)
```

### Operaciones Comunes con Archivos

#### Verificación de Existencia

```python
import os

if os.path.exists('archivo.txt'):
    print('El archivo existe')
```

#### Obtención de Información

```python
import os

# Tamaño del archivo
tamano = os.path.getsize('archivo.txt')

# Última modificación
modificacion = os.path.getmtime('archivo.txt')
```

#### Eliminación de Archivos

```python
import os

if os.path.exists('archivo.txt'):
    os.remove('archivo.txt')
```

## 10. Buenas Prácticas y Recomendaciones

1. **Siempre usar `with`**

   - Garantiza el cierre adecuado del archivo
   - Maneja excepciones automáticamente
   - Código más limpio y seguro

2. **Especificar encoding**

   - Previene problemas de codificación
   - Hace el código más portable
   - Mejora la compatibilidad entre sistemas

3. **Usar buffer apropiado**

   - Mejora el rendimiento
   - Reduce operaciones de E/S
   - Optimiza el uso de recursos

4. **Manejar excepciones**

   - Código más robusto
   - Mejor experiencia de usuario
   - Facilita el debugging

5. **Documentar operaciones**
   - Mejora la mantenibilidad
   - Facilita la colaboración
   - Ayuda en el debugging

---
