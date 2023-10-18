#unity #cSharp[[Data persistence]]
## Descripción

Application.persistentDataPath devuelve el path del directorio de datos persistentes de nuestra aplicación.

En este directorio podemos guardar datos que queramos tener disponibles entre ejecuciones.

Cuando se hace build de iOS o Android, persistentDataPath apunta a un directorio público en el dispositivo. Los archivos solo pueden ser eliminados por el usuario. No se veran afectados por actualizaciones de la app.

Cuando hacemos una build, se generara una GUID basado en el Boundle Identifier. Esta GUID es parte del persistentDataPath. Si lo mantenemos inalterado, futuras actualizaciones seguiran accediendo al mismo dispositivo.


> [!info] 
> - **UWP Apps**: Application.persistentDataPath points to C:\Users\<user>\AppData\LocalLow\<company name>.
> 
> - **Windows Editor and Windows Player**: Application.persistentDataPath usually points to %userprofile%\AppData\LocalLow\<companyname>\<productname>. It is resolved by SHGetKnownFolderPath with FOLDERID_LocalAppDataLow, or SHGetFolderPathW with CSIDL_LOCAL_APPDATA if the former is not available.
> 
> - **WebGL**: Application.persistentDataPath points to` /idbfs/<md5 hash of data path>` where the data path is the URL stripped of everything including and after the last '/' before any '?' components.
>  
> - **Linux**: Application.persistentDataPath points to `$XDG_CONFIG_HOME/unity3d or $HOME/.config/unity3d`.
> 
> - **iOS**: Application.persistentDataPath points to `/var/mobile/Containers/Data/Application/<guid>/Documents`.
>  
> - **tvOS**: Application.persistentDataPath is not supported and returns an empty string.
> 
> - **Android**: Application.persistentDataPath points to `/storage/emulated/<userid>/Android/data/<packagename>/files` on most devices (some older phones might point to location on SD card if present), the path is resolved using android.content.Context.getExternalFilesDir.
>  
> - **Mac**: Application.persistentDataPath points to the user Library folder (This folder is often hidden). In recent Unity releases, user data is written into `~/Library/Application Support/company name/product name`. Older versions of Unity wrote into the `~/Library/Caches` folder, or `~/Library/Application Support/unity.company name.product name`. These folders are all searched for by Unity. The application finds and uses the oldest folder with the required data on your system.