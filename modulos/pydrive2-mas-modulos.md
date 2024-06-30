
# PyDrive2

## Módulos Principales

### pydrive2.auth
- **GoogleAuth**
  - Atributos: <!-- Atributos de pydrive2.auth.GoogleAuth-->
    
    - **credentials**
      - Credenciales OAuth2 actuales.
      - Utilizadas para la autenticación y autorización en Google Drive.

    - **settings**
      - Configuraciones específicas para la autenticación.
      - Incluye atributos como `client_id`, `client_secret`, y otros detalles de configuración.

    - **client_config**
      - Configuración del cliente OAuth.
      - Puede ser proporcionado directamente o cargado desde un archivo.

    - **auth_method**
      - Método de autenticación utilizado.
      - Ejemplos: 'client_secrets', 'service', 'settings'.

    - **flow**
      - Flujo OAuth2 utilizado para la autenticación.
      - Puede ser personalizado si se requiere.

    - **client_config_backend**
      - Backend para cargar la configuración del cliente OAuth.
      - Ejemplos: 'file', 'settings'.

    - **default_settings**
      - Configuraciones predeterminadas para la autenticación.
      - Utilizadas si no se proporciona una configuración específica.

    - **flags**
      - Opciones de línea de comandos para la autenticación.
      - Útil para personalizar el proceso de autenticación.

    - **service**
      - Servicio autenticado de Google Drive.
      - Proporciona acceso a las APIs de Google Drive.

    - **settings_file**
      - Archivo de configuración utilizado para la autenticación.
      - Nombre del archivo de configuración.

    - **http**
      - Objeto HTTP utilizado para realizar solicitudes.
      - Utilizado internamente por la clase para hacer solicitudes HTTP.


  - Métodos:
    - `LocalWebserverAuth()`
    - `CommandLineAuth()`
    - `LoadCredentialsFile(filename)`
    - `SaveCredentialsFile(filename)`
    - `GetAuthUrl()`
    - `CreateAuthUrl()`
    - `Auth()`
    - `Refresh()`
    - `LoadClientConfigFile(filename)`
    - `LoadClientConfigSettings()`
    - `GetFlow()`
    - `GetHttp()`
    - `SetFlow(flow)`

### pydrive2.drive
- **GoogleDrive**
  - Métodos:
    - `CreateFile(metadata=None)`
    - `ListFile(param)`
    - `Auth()`

### pydrive2.files
- **GoogleDriveFile**
  - Métodos:
    - `FetchMetadata(fields='*')`
    - `Upload(param=None)`
    - `FetchContent(mimetype=None)`
    - `GetContentFile(filename, mimetype=None)`
    - `SetContentString(string)`
    - `SetContentFile(filename)`
    - `Delete()`
    - `InsertPermission(param)`
    - `Trash()`
    - `UnTrash()`
    - `FetchPermissions()`
    - `UpdateMetadata(fields)`
    - `GetPermissions()`
    - `DeletePermission(permission_id)`
    - `ListRevisions()`
    - `GetRevision(revision_id)`
    - `UpdateRevision(revision_id, body)`
    - `DeleteRevision(revision_id)`
    - `Copy(metadata=None)`

### pydrive2.settings
- Archivos de configuración (`settings.yaml`)
- Métodos de configuración específicos

### pydrive2.auth.service
- **GoogleAuthService**
  - Métodos:
    - `LoadServiceConfigFile(filename)`
    - `Authorize(service_account_email, scopes)`

## Submódulos

### pydrive2.auth.oauth
- Manejo de OAuth2
  - Métodos para autenticación y renovación de tokens

### pydrive2.auth.token
- Manejo de tokens de autenticación
  - Métodos:
    - `LoadToken()`
    - `SaveToken()`
    - `RefreshToken()`

### pydrive2.files.apiattr
- Atributos y métodos específicos de la API para archivos
  - Métodos adicionales para manejar metadatos y operaciones específicas de la API de Google Drive

### pydrive2.files.file
- Clases y métodos específicos para archivos
  - Métodos adicionales para manejar archivos y carpetas

### pydrive2.fs
- Sistema de archivos virtual (PyFilesystem)
  - Métodos para operaciones de archivos y carpetas

## Ejemplo de Uso

```python
from pydrive2.auth import GoogleAuth
from pydrive2.drive import GoogleDrive

# Autenticación
gauth = GoogleAuth()
gauth.LocalWebserverAuth()

# Crear instancia de GoogleDrive
drive = GoogleDrive(gauth)

# Crear y subir un archivo
file1 = drive.CreateFile({'title': 'Hello.txt'})
file1.SetContentString('Hello World!')
file1.Upload()
print('File uploaded successfully')
```

## Ejemplo de Uso
```python

----

PyDrive2
|
|-- auth
|   |-- GoogleAuth
|       |-- LocalWebserverAuth()
|       |-- CommandLineAuth()
|       |-- LoadCredentialsFile(filename)
|       |-- SaveCredentialsFile(filename)
|       |-- GetAuthUrl()
|       |-- CreateAuthUrl()
|       |-- Auth()
|       |-- Refresh()
|       |-- LoadClientConfigFile(filename)
|       |-- LoadClientConfigSettings()
|       |-- GetFlow()
|       |-- GetHttp()
|       |-- SetFlow(flow)
|   |-- service
|       |-- GoogleAuthService
|           |-- LoadServiceConfigFile(filename)
|           |-- Authorize(service_account_email, scopes)
|   |-- oauth
|   |-- token
|       |-- LoadToken()
|       |-- SaveToken()
|       |-- RefreshToken()
|
|-- drive
|   |-- GoogleDrive
|       |-- CreateFile(metadata=None)
|       |-- ListFile(param)
|       |-- Auth()
|
|-- files
|   |-- GoogleDriveFile
|       |-- FetchMetadata(fields='*')
|       |-- Upload(param=None)
|       |-- FetchContent(mimetype=None)
|       |-- GetContentFile(filename, mimetype=None)
|       |-- SetContentString(string)
|       |-- SetContentFile(filename)
|       |-- Delete()
|       |-- InsertPermission(param)
|       |-- Trash()
|       |-- UnTrash()
|       |-- FetchPermissions()
|       |-- UpdateMetadata(fields)
|       |-- GetPermissions()
|       |-- DeletePermission(permission_id)
|       |-- ListRevisions()
|       |-- GetRevision(revision_id)
|       |-- UpdateRevision(revision_id, body)
|       |-- DeleteRevision(revision_id)
|       |-- Copy(metadata=None)
|   |-- apiattr
|   |-- file
|
|-- settings
|
|-- fs

```






