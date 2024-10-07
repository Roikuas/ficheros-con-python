
# Módulo `sys`

## Introducción
- Proporciona acceso a variables y funciones que interactúan directamente con el intérprete de Python.
- Permite manipular parámetros y funciones del entorno de ejecución.

## Variables Principales
- **`sys.argv`**
  - Lista de argumentos de la línea de comandos.
  - `sys.argv[0]`: Nombre del script.
- **`sys.path`**
  - Lista de rutas donde Python busca los módulos.
  - Se puede modificar para incluir directorios adicionales.
- **`sys.modules`**
  - Diccionario de todos los módulos cargados.
  - Permite acceder a módulos ya importados.
- **`sys.version`**
  - Cadena con la versión de Python.
- **`sys.version_info`**
  - Tupla con información detallada de la versión.
- **`sys.platform`**
  - Identificador de la plataforma (e.g., "win32", "linux").
- **`sys.byteorder`**
  - Orden de bytes del sistema ("little" o "big").
- **`sys.maxsize`**
  - Entero más grande soportado.
- **`sys.prefix` y `sys.exec_prefix`**
  - Directorios de instalación de Python.
- **`sys.copyright`**
  - Información de derechos de autor.
- **`sys.api_version`**
  - Versión de la API de Python.

## Streams Estándar
- **`sys.stdin`**
  - Entrada estándar.
- **`sys.stdout`**
  - Salida estándar.
- **`sys.stderr`**
  - Salida de error estándar.

## Funciones Principales
- **`sys.exit([status])`**
  - Termina el programa.
  - `status`: Código de salida (0 indica éxito).
- **`sys.getsizeof(objeto)`**
  - Retorna el tamaño de un objeto en bytes.
- **`sys.getrefcount(objeto)`**
  - Retorna el conteo de referencias del objeto.
- **`sys.getrecursionlimit()`**
  - Obtiene el límite de recursión.
- **`sys.setrecursionlimit(límite)`**
  - Establece el límite de recursión.
- **`sys.getfilesystemencoding()`**
  - Retorna la codificación del sistema de archivos.
- **`sys.exc_info()`**
  - Retorna información sobre la excepción actual.
- **`sys.getcheckinterval()`** *(Deprecado)*
  - Obtiene el intervalo de chequeo de threads.
- **`sys.setcheckinterval(intervalo)`** *(Deprecado)*
  - Establece el intervalo de chequeo de threads.

## Información del Sistema
- **`sys.platform`**
  - Identificador de la plataforma.
- **`sys.getwindowsversion()`**
  - Información de la versión de Windows (solo en Windows).
- **`sys.implementation`**
  - Información sobre la implementación de Python (e.g., CPython).

## Manejo de Excepciones
- **`sys.exc_info()`**
  - Información de la excepción actual.
- **`sys.last_type`, `sys.last_value`, `sys.last_traceback`**
  - Información de la última excepción no capturada.

## Gestión de Módulos y Importación
- **`sys.path`**
  - Rutas para búsqueda de módulos.
- **`sys.modules`**
  - Módulos ya cargados.
- **`sys.meta_path`**
  - Lista de meta path finders para importar módulos.

## Configuración y Flags
- **`sys.dont_write_bytecode`**
  - Evita la creación de archivos `.pyc`.
- **`sys.flags`**
  - Bandera de opciones de ejecución (e.g., optimización).
- **`sys.abiflags`**
  - Bandera de la interfaz binaria de funciones.
- **`sys.builtin_module_names`**
  - Nombres de módulos incorporados.

## Uso Avanzado
- **`sys.settrace(función)`**
  - Establece una función de trace para depuración.
- **`sys.gettrace()`**
  - Obtiene la función de trace actual.
- **`sys.setswitchinterval(intervalo)`**
  - Establece el intervalo de cambio de contexto de threads.
- **`sys.getswitchinterval()`**
  - Obtiene el intervalo de cambio de contexto de threads.

## Ejemplos de Uso
- **Acceder a argumentos de línea de comandos:**
  ```python
  import sys
  print(sys.argv)
  ```
- **Salir del programa con un código de estado:**
  ```python
  import sys
  sys.exit(0)
  ```
- **Modificar la ruta de búsqueda de módulos:**
  ```python
  import sys
  sys.path.append('/ruta/a/mi/modulo')
  ```

## Consideraciones
- **Portabilidad:**
  - Algunas funciones y variables son específicas de la plataforma.
- **Seguridad:**
  - Manipular `sys.path` y `sys.modules` puede afectar la seguridad y estabilidad del programa.
- **Deprecaciones:**
  - Algunas funciones como `sys.getcheckinterval()` están deprecadas y no deben usarse en nuevas aplicaciones.
