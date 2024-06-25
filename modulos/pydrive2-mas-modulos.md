
# PyDrive2

## Módulos Principales

### pydrive2.auth
- **GoogleAuth**
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






