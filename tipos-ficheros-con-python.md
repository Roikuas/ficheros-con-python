
# Tipos de Ficheros en Python y Bibliotecas Asociadas

## 1. Ficheros de Texto
- `.txt`
  - **Módulo:** `open`, `io`
  - **Descripción:** Lectura y escritura de archivos de texto plano.
- `.csv`
  - **Módulo:** `csv`, `pandas`
  - **Descripción:** Manipulación de archivos de valores separados por comas.
- `.log`
  - **Módulo:** `open`, `logging`
  - **Descripción:** Gestión de archivos de registro de eventos.
- `.md`
  - **Módulo:** `markdown`
  - **Descripción:** Procesamiento de archivos Markdown.

## 2. Ficheros Binarios
- `.bin`
  - **Módulo:** `open`, `struct`
  - **Descripción:** Lectura y escritura de archivos binarios.
- `.dat`
  - **Módulo:** `open`, `pickle`
  - **Descripción:** Manipulación de archivos de datos binarios.

## 3. Ficheros JSON
- `.json`
  - **Módulo:** `json`
  - **Descripción:** Manipulación de datos en formato JSON.

## 4. Ficheros XML
- `.xml`
  - **Módulo:** `xml.etree.ElementTree`, `lxml`
  - **Descripción:** Procesamiento y análisis de datos XML.

## 5. Ficheros de Configuración
- `.ini`
  - **Módulo:** `configparser`
  - **Descripción:** Manejo de archivos de configuración en formato INI.
- `.cfg`
  - **Módulo:** `configparser`
  - **Descripción:** Similar a los archivos INI para configuraciones.

## 6. Ficheros de Microsoft Excel
- `.xls`
  - **Módulo:** `xlrd`, `xlwt`
  - **Descripción:** Lectura de archivos Excel antiguos.
- `.xlsx`
  - **Módulo:** `openpyxl`, `pandas`
  - **Descripción:** Lectura y escritura de archivos Excel modernos.

## 7. Ficheros de Microsoft Word
- `.doc`
  - **Módulo:** `python-docx`
  - **Descripción:** Manipulación de documentos Word.
- `.docx`
  - **Módulo:** `python-docx`
  - **Descripción:** Manipulación de documentos Word.

## 8. Ficheros PDF
- `.pdf`
  - **Módulo:** `PyPDF2`, `pdfminer.six`, `reportlab`
  - **Descripción:** Lectura, escritura y creación de archivos PDF.

## 9. Ficheros de Imagen
- `.jpg`, `.jpeg`, `.png`, `.gif`, `.bmp`, `.tiff`
  - **Módulo:** `Pillow`
  - **Descripción:** Manipulación de imágenes.

## 10. Ficheros de Audio
- `.mp3`
  - **Módulo:** `pydub`, `mp3file`
  - **Descripción:** Manipulación de archivos de audio MP3.
- `.wav`
  - **Módulo:** `wave`, `pyaudio`
  - **Descripción:** Manipulación de archivos de audio WAV.
- `.aac`
  - **Módulo:** `pydub`
  - **Descripción:** Manipulación de archivos de audio AAC.
- `.flac`
  - **Módulo:** `pydub`
  - **Descripción:** Manipulación de archivos de audio FLAC.

## 11. Ficheros de Video
- `.mp4`, `.avi`, `.mkv`, `.mov`, `.wmv`
  - **Módulo:** `opencv-python`, `moviepy`, `ffmpeg-python`
  - **Descripción:** Manipulación y procesamiento de archivos de video.

## 12. Ficheros de Base de Datos
- `.db`, `.sqlite`
  - **Módulo:** `sqlite3`
  - **Descripción:** Manipulación de bases de datos SQLite.
- `.sql`
  - **Módulo:** `sqlite3`, `sqlalchemy`
  - **Descripción:** Manipulación de archivos SQL.

## 13. Ficheros de Hojas de Cálculo
- `.ods`
  - **Módulo:** `ezodf`, `pandas`
  - **Descripción:** Lectura y escritura de archivos de hojas de cálculo OpenDocument.
- `.tsv`
  - **Módulo:** `csv`, `pandas`
  - **Descripción:** Manipulación de archivos de valores separados por tabulaciones.

## 14. Ficheros Comprimidos
- `.zip`
  - **Módulo:** `zipfile`
  - **Descripción:** Manipulación de archivos comprimidos ZIP.
- `.tar`, `.gz`, `.bz2`
  - **Módulo:** `tarfile`
  - **Descripción:** Manipulación de archivos comprimidos TAR, GZIP y BZIP2.
- `.7z`
  - **Módulo:** `py7zr`
  - **Descripción:** Manipulación de archivos comprimidos 7-Zip.
- `.rar`
  - **Módulo:** `rarfile`
  - **Descripción:** Manipulación de archivos comprimidos RAR.

## 15. Ficheros de Presentación
- `.ppt`, `.pptx`
  - **Módulo:** `python-pptx`
  - **Descripción:** Manipulación de presentaciones PowerPoint.

## 16. Ficheros HTML
- `.html`, `.htm`
  - **Módulo:** `html.parser`, `BeautifulSoup`
  - **Descripción:** Análisis y manipulación de archivos HTML.

## 17. Ficheros de Scripts y Programación
- `.py`
  - **Módulo:** `open`
  - **Descripción:** Archivos de scripts Python.
- `.js`
  - **Módulo:** `open`
  - **Descripción:** Archivos de scripts JavaScript.
- `.html`, `.css`
  - **Módulo:** `open`
  - **Descripción:** Archivos de código HTML y CSS.

## 18. Ficheros de Virtualización
- `.iso`
  - **Módulo:** `os`, `subprocess`
  - **Descripción:** Manipulación de imágenes de disco ISO.
- `.vmdk`
  - **Módulo:** `os`, `subprocess`
  - **Descripción:** Manipulación de discos virtuales VMware.
- `.ova`
  - **Módulo:** `os`, `subprocess`
  - **Descripción:** Manipulación de archivos de aplicaciones virtuales.

## 19. Otros Tipos de Ficheros
- `.yaml` / `.yml`
  - **Módulo:** `pyyaml`
  - **Descripción:** Manipulación de archivos YAML.
- `.pickle`
  - **Módulo:** `pickle`
  - **Descripción:** Serialización y deserialización de objetos Python.
- `.parquet`
  - **Módulo:** `pyarrow`, `pandas`
  - **Descripción:** Manipulación de archivos de datos Parquet.
- `.avro`
  - **Módulo:** `fastavro`, `avro`
  - **Descripción:** Manipulación de archivos de datos Avro.

