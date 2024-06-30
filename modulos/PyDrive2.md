
---
markmap:
  maxWidth: 300
  embedAssets: true
  initialExpandLevel: 1
---

 # Mapa Mental: Módulos y Funciones Detalladas de PyDrive2

## GoogleAuth
- `GoogleAuth`: Módulo para la autenticación con Google Drive.
  - `LocalWebserverAuth()`: Método para la autenticación usando un servidor web local.
  - `ServiceAccountAuth()`: Autenticación usando una cuenta de servicio.
  - `Auth()`: Autenticación genérica.
  - `LoadCredentials() / SaveCredentials()`: Métodos para cargar y guardar credenciales de autenticación.
  - `LocalWebserverOAuth2()`: Flujo de autenticación OAuth2 utilizando un servidor web local.

## GoogleDrive
- `GoogleDrive`: Módulo principal para interactuar con Google Drive.
  - `CreateFile()`: Crear un nuevo archivo en Google Drive.
  - `ListFile() / GetFileList()`: Listar archivos y obtener la lista completa de archivos.
  - `DeleteFile()`: Eliminar un archivo de Google Drive.
  - `CreateFolder()`: Crear una nueva carpeta en Google Drive.
  - `ListFolders()`: Listar todas las carpetas en Google Drive.
  - `DeleteFolder()`: Eliminar una carpeta de Google Drive.
  - `SearchFiles()`: Realizar una búsqueda avanzada de archivos.
  - `GetPermissions()`: Obtener los permisos de un archivo o carpeta.
  - `InsertPermission()`: Insertar un nuevo permiso para compartir un archivo o carpeta.
  - `DeletePermission()`: Eliminar un permiso de un archivo o carpeta.

## Files
- `Files`: Módulo para la gestión y manipulación de archivos en Google Drive.
  - `ApiRequestError`: Excepción que maneja errores específicos de las solicitudes a la API.
  - Clases de archivos:
    - `File`: Representa un archivo genérico en Google Drive.
    - `GoogleDriveFile`: Proporciona métodos específicos para archivos de Google Drive.
    - `GoogleDriveFileList`: Representa una lista de archivos de Google Drive.
    - `GoogleDriveFileMetadata`: Metadatos de un archivo en Google Drive.

## Settings
- `Settings`: Módulo para la configuración de PyDrive2.
  - `ChangeHttpProxy()`: Cambiar la configuración del proxy HTTP utilizado por PyDrive2.
  - `GetSettings() / SetSettings()`: Métodos para obtener y establecer configuraciones específicas de PyDrive2.

## Utilities
- `Utilities`: Módulo que proporciona utilidades adicionales para trabajar con PyDrive2.
  - `Html2Text()`: Convertir HTML a texto plano.
  - `LoadJsonFile() / SaveJsonFile()`: Cargar y guardar archivos en formato JSON.
  - `LoadSettingsFile() / SaveSettingsFile()`: Cargar y guardar archivos de configuración específicos de PyDrive2.

