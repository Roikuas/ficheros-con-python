# Conceptos Clave para Usar Openpyxl

## Introducción a Openpyxl

- **Openpyxl**: Librería de Python para trabajar con archivos de Excel (.xlsx).

## Estructura de Archivos Excel

- **Workbook**: Representa todo el libro de Excel.
- **Worksheet**: Hojas individuales dentro del libro.
- **Cell**: Celda individual dentro de una hoja.

## Lectura y Escritura de Archivos

- **load_workbook()**: Cargar un archivo Excel existente.
- **Workbook.save()**: Guardar cambios en un archivo Excel.
- **create_sheet()**: Crear una nueva hoja en un libro.

## Acceso y Modificación de Datos

- **sheet['A1']**: Acceder a una celda por coordenadas.
- **sheet.cell()**: Acceder a una celda por fila y columna.
- **value**: Propiedad para obtener o asignar el valor de una celda.

## Operaciones con Filas y Columnas

- **iter_rows()**: Iterar sobre filas.
- **iter_cols()**: Iterar sobre columnas.
- **append()**: Agregar filas al final de una hoja.

## Estilo y Formato

- **Font()**: Configurar el estilo de la fuente.
- **Alignment()**: Alinear el contenido de las celdas.
- **NumberFormat()**: Formatear números en celdas.

## Gráficos y Objetos

- **add_chart()**: Agregar un gráfico a una hoja.
- **Image()**: Insertar imágenes en una hoja.

## Manejo de Fórmulas

- **data_only**: Obtener valores calculados en lugar de fórmulas.
- **Formula()**: Asignar fórmulas a celdas.

## Manejo Avanzado

- **Merging**: Combinar celdas.
- **Data Validation**: Validar datos de entrada en celdas.

## Optimización y Rendimiento

- **pandas.DataFrame.to_excel()**: Exportar datos desde Pandas a Excel con Openpyxl.

## Seguridad y Protección

- **Protection**: Proteger hojas y libros contra modificaciones no autorizadas.

## Integración con Otras Bibliotecas

- Compatibilidad con otras bibliotecas de Python como Pandas para manipulación de datos avanzada.


