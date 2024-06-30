
# Mapa Mental Completo: Módulo `pickle` en Python

## pickle
- Serialización y deserialización de objetos Python en formato binario
- Compatible solo con Python

### Funciones Principales

#### Serialización

- **pickle.dumps()**
  - Convierte un objeto Python a una representación en bytes
  - Sintaxis: `pickle.dumps(objeto)`
    - `objeto`: Objeto Python a serializar
  - Ejemplo:
    ```python
    import pickle
    
    datos = {'nombre': 'John', 'edad': 30, 'ciudad': 'New York'}
    datos_serializados = pickle.dumps(datos)
    ```

- **pickle.dump()**
  - Escribe un objeto Python serializado en un archivo binario
  - Sintaxis: `pickle.dump(objeto, archivo)`
    - `objeto`: Objeto Python a serializar
    - `archivo`: Archivo donde se escribirá la salida
  - Ejemplo:
    ```python
    with open('datos.pickle', 'wb') as archivo:
        pickle.dump(datos, archivo)
    ```

#### Deserialización

- **pickle.loads()**
  - Convierte una representación en bytes a un objeto Python
  - Sintaxis: `pickle.loads(bytes_obj)`
    - `bytes_obj`: Objeto en bytes a deserializar
  - Ejemplo:
    ```python
    datos_recuperados = pickle.loads(datos_serializados)
    ```

- **pickle.load()**
  - Lee y deserializa un archivo binario en un objeto Python
  - Sintaxis: `pickle.load(archivo)`
    - `archivo`: Archivo binario a leer y deserializar
  - Ejemplo:
    ```python
    with open('datos.pickle', 'rb') as archivo:
        datos_recuperados = pickle.load(archivo)
    ```

### Limitaciones y Consideraciones

- **Compatibilidad**: Los archivos pickle solo son legibles por Python y dependen de la versión de Python utilizada.
- **Seguridad**: Puede ser riesgoso cargar datos pickle no confiables debido a posibles vulnerabilidades de seguridad.

### Aplicaciones Comunes

- **Almacenamiento de Estructuras de Datos Complejas**: Permite guardar y recuperar objetos complejos de manera eficiente.
- **Comunicación entre Procesos Python**: Facilita el intercambio de datos entre procesos o a través de redes.
- **Persistencia de Modelos de Machine Learning**: Útil para guardar y cargar modelos entrenados en aplicaciones de aprendizaje automático.

### Ejemplo de Uso Completo

```python
import pickle

# Serializar un diccionario a un archivo pickle
datos = {'nombre': 'John', 'edad': 30, 'ciudad': 'New York'}
with open('datos.pickle', 'wb') as archivo:
    pickle.dump(datos, archivo)

# Leer y deserializar un archivo pickle
with open('datos.pickle', 'rb') as archivo:
    datos_recuperados = pickle.load(archivo)
    print(datos_recuperados['nombre'])
