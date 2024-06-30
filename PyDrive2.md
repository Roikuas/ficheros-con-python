
# Explicación de Métodos en PyDrive2

## Auth
- `GoogleAuth()`: Inicia el proceso de autenticación con Google.
  - `DefaultCredentials()`: Obtiene las credenciales predeterminadas.
  - `LocalWebserverAuth()`: Realiza la autenticación a través de un servidor web local.
  - `ServiceAuth()`: Autenticación usando credenciales de servicio.
  - `Auth()`: Realiza la autenticación.
  - `AuthServiceAccount()`: Autenticación usando una cuenta de servicio.

## Drive
- `GoogleDrive(auth)`: Crea una instancia de GoogleDrive con el objeto de autenticación proporcionado.
  - `CreateFile()`: Crea un nuevo archivo en Google Drive.
    - `SetContentFile(file_path)`: Establece el contenido del archivo a subir.
    - `Upload()`: Sube el archivo al Google Drive.
  - `ListFile()`: Lista los archivos en Google Drive.
  - `GetList()`: Obtiene una lista detallada de archivos.
  - `Delete(file_id)`: Elimina un archivo de Google Drive.
  - `Trash(file_id)`: Mueve un archivo a la papelera.
  - `Untrash(file_id)`: Restaura un archivo de la papelera.
  - `CreateFolder(folder_name)`: Crea una nueva carpeta en Google Drive.
  - `GetPermissions(file_id)`: Obtiene los permisos de un archivo.
  - `InsertPermission(file_id, permission)`: Inserta un nuevo permiso en un archivo.
  - `Auth()`: Realiza la autenticación nuevamente si es necesario.
  - `GetAbout()`: Obtiene información general sobre la cuenta de Google Drive.
  - `GetFile(file_id)`: Obtiene la información de un archivo específico.
  - `GetFileList()`: Obtiene la lista de archivos en Google Drive.
  - `GetRevisions(file_id)`: Obtiene las revisiones de un archivo.
  - `GetUploadFolder()`: Obtiene la carpeta de subida predeterminada.
  - `ImportFile(file_id, metadata)`: Importa un archivo a Google Drive.
  - `InsertFile(file_metadata)`: Inserta un archivo en Google Drive.
  - `InsertFolder(folder_metadata)`: Inserta una carpeta en Google Drive.
  - `MoveFile(file_id, new_folder_id)`: Mueve un archivo a otra carpeta.
  - `MoveToFolder(file_id, new_folder_id)`: Mueve un archivo a una carpeta específica.
  - `UpdateFile(file_id, file_metadata)`: Actualiza la información de un archivo.
  - `UpdateFileContent(file_id, new_content)`: Actualiza el contenido de un archivo.
  - `Upload(file_metadata, file_content)`: Sube un archivo con metadatos y contenido.
  - `VerifyUpload(file_id)`: Verifica si la subida de un archivo ha sido completada.
  - `WaitUntilComplete(request)`: Espera hasta que una solicitud esté completa.

## Settings
- `GoogleDriveSettings()`: Gestiona las configuraciones de Google Drive.
  - `SetSettings(settings)`: Establece las configuraciones específicas.
  - `LoadSettings()`: Carga las configuraciones guardadas.
  - `Load(file_id)`: Carga las configuraciones de un archivo específico.
  - `SaveSettings()`: Guarda las configuraciones actuales.
  - `UpdateSettings(settings)`: Actualiza las configuraciones existentes.

## Utils
- `ImportGoogleDrive`: Utilidades adicionales para Google Drive.
  - `drive()`: Accede a la unidad de Google Drive.
  - `drivefiles()`: Accede a los archivos de Google Drive.
  - `findfile(query)`: Busca un archivo específico.
  - `getfile(file_id)`: Obtiene la información de un archivo por su ID.
