# Errores comunes al manejar archivos en Python

## 1. FileNotFoundError

```python
try:
    with open("archivo_que_no_existe.txt", "r") as file:
        contenido = file.read()
except FileNotFoundError:
    print("El archivo no existe.")
```

**Explicación**: Este error ocurre cuando se intenta abrir un archivo que no está presente en la ubicación especificada.
**Posibles variantes**:

- Ruta mal escrita.
- Archivo eliminado o movido.

---

## 2. PermissionError

```python
try:
    with open("/archivo_protegido.txt", "w") as file:
        file.write("Texto")
except PermissionError:
    print("No se tienen permisos para escribir en el archivo.")
```

**Explicación**: Este error surge al intentar acceder a un archivo sin los permisos adecuados, como lectura o escritura.
**Posibles variantes**:

- Intentar escribir en un archivo de solo lectura.
- Falta de permisos de administrador.

---

## 3. ValueError

```python
try:
    with open("archivo.txt", "invalid_mode") as file:
        contenido = file.read()
except ValueError:
    print("Modo inválido para abrir el archivo.")
```

**Explicación**: Se genera cuando se pasa un argumento inválido al método `open()`, como un modo de apertura inexistente.
**Posibles variantes**:

- Modos no válidos como "readwrite" en lugar de "r+".

---

## 4. IsADirectoryError

```python
try:
    with open("/directorio/", "r") as file:
        contenido = file.read()
except IsADirectoryError:
    print("No se puede abrir un directorio como archivo.")
```

**Explicación**: Aparece al intentar tratar un directorio como si fuera un archivo.
**Posibles variantes**:

- Pasar una ruta de directorio en lugar de un archivo.

---

## 5. NotADirectoryError

```python
import os
try:
    os.listdir("archivo.txt")
except NotADirectoryError:
    print("No se puede tratar un archivo como un directorio.")
```

**Explicación**: Este error ocurre cuando se intenta tratar un archivo regular como un directorio.
**Posibles variantes**:

- Usar funciones de directorio como `os.listdir()` en archivos regulares.

---

## 6. UnicodeDecodeError

```python
try:
    with open("archivo_binario.dat", "r", encoding="utf-8") as file:
        contenido = file.read()
except UnicodeDecodeError:
    print("Error de codificación al leer el archivo.")
```

**Explicación**: Este error ocurre al intentar leer un archivo con una codificación incorrecta.
**Posibles variantes**:

- Leer un archivo binario como texto.
- Usar una codificación inadecuada, como UTF-8 en lugar de ISO-8859-1.

---

## 7. TypeError

```python
try:
    with open(123, "r") as file:
        contenido = file.read()
except TypeError:
    print("Tipo de argumento inválido para open().")
```

**Explicación**: Se genera cuando los argumentos pasados a `open()` no son del tipo esperado.
**Posibles variantes**:

- Pasar un número en lugar de una cadena como nombre de archivo.

---

## 8. UnsupportedOperation

```python
try:
    with open("archivo.txt", "r") as file:
        file.write("Texto")
except UnsupportedOperation:
    print("No se puede escribir en un archivo abierto en modo lectura.")
```

**Explicación**: Este error aparece cuando se intenta realizar una operación no permitida en el modo de apertura del archivo.
**Posibles variantes**:

- Escribir en un archivo abierto en modo "r".

---

## 9. OSError

```python
try:
    with open("archivo_grande.txt", "w") as file:
        file.write("A" * 10**10)
except OSError:
    print("Error al manejar el archivo, posiblemente por espacio insuficiente.")
```

**Explicación**: Error genérico relacionado con operaciones de sistema en archivos.
**Posibles variantes**:

- Disco lleno.
- Ruta de archivo demasiado larga.

---

## 10. IOError

```python
try:
    with open("/red/remoto.txt", "r") as file:
        contenido = file.read()
except IOError:
    print("Error al acceder al archivo remoto.")
```

**Explicación**: Error relacionado con operaciones de entrada/salida, como problemas de red o dispositivos.
**Posibles variantes**:

- Archivo en una red inaccesible.

---

## 11. MemoryError

```python
try:
    with open("archivo_grande.txt", "rb") as file:
        contenido = file.read()
except MemoryError:
    print("El archivo es demasiado grande para la memoria disponible.")
```

**Explicación**: Ocurre al intentar cargar en memoria un archivo más grande de lo que el sistema puede manejar.
**Posibles variantes**:

- Leer archivos gigantes sin usar buffers.

---

## 12. FileExistsError

```python
import os
try:
    os.mkdir("directorio_existente")
except FileExistsError:
    print("El directorio ya existe.")
```

**Explicación**: Surge al intentar crear un archivo o directorio que ya existe.
**Posibles variantes**:

- Crear un archivo con el mismo nombre de un directorio.

---

## 13. FileDescriptorError

```python
import os
try:
    os.read(-1, 1024)
except OSError:
    print("Descriptor de archivo inválido.")
```

**Explicación**: Este error ocurre al usar un descriptor de archivo inválido.
**Posibles variantes**:

- Usar un descriptor cerrado o no asignado.

---

## 14. BlockingIOError

```python
import os
try:
    os.read(os.open("archivo.txt", os.O_NONBLOCK), 1024)
except BlockingIOError:
    print("La operación no bloqueante falló temporalmente.")
```

**Explicación**: Error relacionado con operaciones no bloqueantes, como lecturas o escrituras interrumpidas.
**Posibles variantes**:

- Intentar leer en un socket sin datos disponibles.

---

## 15. NameError

```python
try:
    with open(archivo_inexistente, "r") as file:
        contenido = file.read()
except NameError:
    print("La variable utilizada no está definida.")
```

**Explicación**: Se genera al usar una variable que no ha sido definida previamente.
**Posibles variantes**:

- Uso de nombres mal escritos.

---

## 16. KeyError

```python
config = {"path": "archivo.txt"}
try:
    with open(config["invalid_key"], "r") as file:
        contenido = file.read()
except KeyError:
    print("La clave no existe en el diccionario.")
```

**Explicación**: Este error ocurre al intentar acceder a una clave inexistente en un diccionario.
**Posibles variantes**:

- Usar claves incorrectas o mal escritas.

---

## 17. AttributeError

```python
try:
    with open("archivo.txt", "r") as file:
        file.nonexistent_method()
except AttributeError:
    print("El método no existe en el objeto archivo.")
```

**Explicación**: Aparece al intentar llamar un método o atributo que no existe en el objeto.
**Posibles variantes**:

- Usar métodos incorrectos o mal escritos.

---

## 18. EOFError

```python
try:
    with open("archivo_vacio.txt", "r") as file:
        input(file.read())
except EOFError:
    print("Se alcanzó el final del archivo.")
```

**Explicación**: Error que ocurre al intentar leer más allá del final de un archivo.
**Posibles variantes**:

- Uso incorrecto de métodos de lectura.

---

## 19. InterruptedError

```python
import signal
import time

def handler(signum, frame):
    raise InterruptedError("Operación interrumpida")

try:
    signal.signal(signal.SIGALRM, handler)
    signal.alarm(1)
    time.sleep(2)
except InterruptedError:
    print("La operación fue interrumpida por una señal externa.")
```

**Explicación**: Este error aparece cuando una señal externa interrumpe la operación en curso.
**Posibles variantes**:

- Señales del sistema que detienen una operación.
- Interrupciones manuales por el usuario.

---

## 20. TimeoutError

```python
import socket

try:
    sock = socket.create_connection(("8.8.8.8", 53), timeout=0.001)
except TimeoutError:
    print("La operación excedió el tiempo límite.")
```

**Explicación**: Este error ocurre cuando una operación, como conectar a un socket, supera el tiempo límite configurado.
**Posibles variantes**:

- Operaciones de red con tiempo de espera configurado.
- Intentos de conexión a servidores no accesibles.
