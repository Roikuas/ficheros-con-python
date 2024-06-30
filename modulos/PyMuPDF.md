# Mapa Mental Completo: Módulo `PyMuPDF` en Python

## PyMuPDF
- Biblioteca para trabajar con archivos PDF en Python
- Proporciona capacidades para leer, escribir y manipular documentos PDF

### Funcionalidades Principales

#### Lectura de Documentos PDF

- **Abrir Documento**
  - `fitz.open()`: Abre un archivo PDF y devuelve un objeto `Document`

- **Obtener Metadatos**
  - `Document.metadata`: Devuelve metadatos del documento PDF (autor, título, etc.)

- **Número de Páginas**
  - `Document.page_count`: Devuelve el número total de páginas en el documento

#### Manipulación de Páginas y Texto

- **Acceder a Páginas**
  - `Document.load_page(n)`: Carga la página `n` del documento
  - `Page.get_text()`: Extrae el texto de la página actual

- **Buscar Texto**
  - `Page.search_for(pattern)`: Busca un patrón de texto en la página

#### Manipulación Avanzada

- **Extraer Imágenes**
  - `Page.get_pixmap()`: Extrae la imagen de la página en forma de mapa de bits

- **Análisis de Estructura**
  - `Page.get_page_layout()`: Devuelve una representación de la estructura de la página

#### Exportación y Guardado

- **Guardar Páginas como Imágenes**
  - `Page.save_image()`: Guarda la página como una imagen

- **Guardar Páginas como Texto**
  - `Document.save_text()`: Guarda el texto del documento en un archivo de texto

### Ejemplo de Uso

```python
import fitz

# Abrir un documento PDF
documento = fitz.open('ejemplo.pdf')

# Obtener metadatos
metadatos = documento.metadata
print(f"Metadatos del documento: {metadatos}")

# Acceder a la primera página
primera_pagina = documento.load_page(0)

# Extraer texto de la primera página
texto_pagina = primera_pagina.get_text()
print(f"Texto de la primera página:\n{texto_pagina}")

# Buscar y resaltar un texto específico en la página
busqueda = primera_pagina.search_for('ejemplo')
for marca in busqueda:
    primera_pagina.add_highlight_annot(marca)

# Guardar el documento modificado
documento.save('documento_modificado.pdf')

# Cerrar el documento
documento.close()

