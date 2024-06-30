
# Conceptos Clave para Usar PyPDF2

## Introducción a PyPDF2

- **PyPDF2**: Librería de Python para manipular archivos PDF.

## Operaciones Básicas

- **PdfFileReader**: Clase para leer un archivo PDF.
  - `getNumPages()`: Obtener el número de páginas.
  - `getPage()`: Obtener un objeto de página específica.

- **PdfFileWriter**: Clase para crear un nuevo archivo PDF o modificar uno existente.
  - `addPage()`: Agregar una página al archivo de salida.
  - `write()`: Escribir el contenido modificado en un archivo.

## Extracción de Texto

- **extractText()**: Método para extraer texto de una página PDF.

## Operaciones Avanzadas

- **Manipulación de Páginas**:
  - `mergePage()`: Combinar el contenido de dos páginas en una.
  - `addBlankPage()`: Agregar una página en blanco al archivo.

- **Rotación**:
  - `rotateClockwise()`, `rotateCounterClockwise()`: Rotar una página en sentido horario o antihorario.

## Manejo de Marcadores y Metadatos

- **Marcadores**:
  - `addBookmark()`: Agregar un marcador en el documento.

- **Metadatos**:
  - `getDocumentInfo()`: Obtener información del documento (título, autor, etc.).

## Protección y Seguridad

- **Encriptación**:
  - `encrypt()`: Proteger el documento con una contraseña.

## Fusión y División de PDFs

- **Fusión**:
  - Combinar varios archivos PDF en uno solo.

- **División**:
  - Dividir un PDF en varios archivos más pequeños.

## Manipulación de Imágenes

- **Extracción**:
  - Extraer imágenes incrustadas en el PDF.

## Optimización y Rendimiento

- **Uso Eficiente de Recursos**:
  - Manejo adecuado de la memoria y los recursos al trabajar con archivos PDF grandes.

## Compatibilidad y Soporte

- **Compatibilidad**: Funciona con la mayoría de los archivos PDF estándar, tanto para lectura como escritura.

## Integración con Otras Bibliotecas

- Puede combinarse con otras bibliotecas de Python para análisis de datos o generación de informes.

