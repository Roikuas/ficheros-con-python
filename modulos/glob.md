
# Mapa Mental Completo: Módulo `glob` en Python

## glob
- Búsqueda de archivos y directorios que coinciden con un patrón
- Uso de comodines estilo Unix

### Funciones Principales

#### glob()
- Busca archivos y directorios que coinciden con un patrón
- Sintaxis: `glob.glob(pattern, recursive=False)`
- Parámetros:
  - `pattern`: Patrón de búsqueda (puede incluir comodines `*`, `?`, `[]`)
  - `recursive`: Permite búsqueda recursiva en subdirectorios si es `True`
- Devuelve: Lista de rutas que coinciden con el patrón

#### iglob()
- Generador que busca archivos y directorios que coinciden con un patrón
- Sintaxis: `glob.iglob(pattern, recursive=False)`
- Parámetros:
  - `pattern`: Patrón de búsqueda
  - `recursive`: Permite búsqueda recursiva en subdirectorios si es `True`
- Devuelve: Generador de rutas que coinciden con el patrón

### Comodines
- **`*`**: Coincide con cero o más caracteres
- **`?`**: Coincide con un solo carácter
- **`[abc]`**: Coincide con cualquiera de los caracteres entre corchetes
- **`[!abc]`**: Coincide con cualquiera de los caracteres que no están entre corchetes
- **`[a-z]`**: Coincide con cualquier carácter en el rango especificado

### Ejemplos de Uso

#### Búsqueda Simple
```python
import glob

# Buscar todos los archivos .txt en el directorio actual
archivos_txt = glob.glob('*.txt')
print(archivos_txt)
