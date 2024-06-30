
# Mapa Mental Completo: Módulo `pandas` en Python

## pandas
- Biblioteca de análisis de datos que ofrece estructuras de datos flexibles y herramientas para manipular datos tabulares y series temporales

### Estructuras de Datos Principales

#### DataFrame

- Estructura tabular bidimensional con etiquetas en filas y columnas
- Similar a una tabla de base de datos o una hoja de cálculo

#### Series

- Objeto unidimensional similar a un array o lista que contiene datos y etiquetas de ejes (índices)

### Funcionalidades Principales

#### Lectura y Escritura de Datos

- **Lectura de Datos**
  - `pd.read_csv()`: Lee datos desde un archivo CSV en un DataFrame
  - `pd.read_excel()`: Lee datos desde un archivo Excel en un DataFrame
  - `pd.read_sql()`: Lee datos desde una base de datos SQL en un DataFrame

- **Escritura de Datos**
  - `df.to_csv()`: Escribe datos de un DataFrame en un archivo CSV
  - `df.to_excel()`: Escribe datos de un DataFrame en un archivo Excel
  - `df.to_sql()`: Escribe datos de un DataFrame en una base de datos SQL

#### Manipulación y Transformación de Datos

- **Selección y Filtrado**
  - `df[columna]`: Selecciona una columna específica del DataFrame
  - `df.loc[]`: Accede a un grupo de filas y columnas por etiqueta(s) o una matriz booleana
  - `df.iloc[]`: Accede a un grupo de filas y columnas por posición(s) enteras

- **Operaciones de Datos**
  - `df.merge()`: Realiza una combinación (join) de DataFrame similar a SQL
  - `df.groupby()`: Agrupa filas por una o más columnas
  - `df.pivot_table()`: Crea una tabla dinámica a partir de un DataFrame

#### Análisis y Visualización de Datos

- **Estadísticas Descriptivas**
  - `df.describe()`: Calcula estadísticas descriptivas para columnas numéricas

- **Visualización**
  - `df.plot()`: Crea gráficos a partir de los datos del DataFrame utilizando matplotlib integrado

### Funcionalidades Avanzadas

- **Manejo de Fechas y Series Temporales**
  - `pd.date_range()`: Genera un rango de fechas
  - `pd.to_datetime()`: Convierte una cadena, serie temporal o lista en tipo de fecha y hora
  - `df.resample()`: Cambia la frecuencia de los datos de la serie temporal

- **Manejo de Datos Faltantes**
  - `df.dropna()`: Elimina filas o columnas con datos faltantes
  - `df.fillna()`: Rellena valores faltantes con un valor específico

### Ejemplo de Uso

```python
import pandas as pd

# Crear un DataFrame
datos = {'Nombre': ['John', 'Emily', 'Jack'],
         'Edad': [30, 28, 35],
         'Ciudad': ['New York', 'Los Angeles', 'Chicago']}
df = pd.DataFrame(datos)

# Mostrar el DataFrame
print(df)

# Estadísticas descriptivas
print(df.describe())

# Graficar datos
df.plot(x='Nombre', y='Edad', kind='bar', title='Edades por Nombre')

# Guardar el DataFrame en un archivo CSV
df.to_csv('datos.csv', index=False)
