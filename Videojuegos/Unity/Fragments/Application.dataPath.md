 #unity #cSharp[[Data persistence]]

## Descripción
No debe ser utilizado para guardar informacion en runtime porque en algunos dispositivos es de solo lectura. Para ello es mejor usar: [[Application.persitentDataPath]]
Application.DataPath devuelve el path del directorio de datos de nuestra aplicación.

Es distinto para cada dispositivo.

> [!info] 
> - **Unity Editor:** `<_path to project folder_>/Assets`
> 
> - **Mac player:** `<_path to player app bundle_>/Contents`
> 
> - **iOS player:** `<_path to player app bundle_>/<_AppName.app_>/Data` (this folder is read only, use [Application.persistentDataPath](https://docs.unity3d.com/ScriptReference/Application-persistentDataPath.html) to save data).
> 
> - **Win/Linux player:** `<_path to executablename_Data folder_> `(note that most Linux installations will be case-sensitive!)
> 
> - **WebGL:** The absolute url to the player data file folder (without the actual data file name)
> 
> - **Android:** Normally it points directly to the APK. If you are running a split binary build, it points to the [OBB](https://docs.unity3d.com/Manual/android-OBBsupport.html) instead.
> 
> - **UWP Apps:** The absolute path to the player data folder (this folder is read only.

> [!example] 
> 
> 
> ``` csharp
> //Attach this script to a [GameObject](https://docs.unity3d.com/ScriptReference/GameObject.html)
> //This script outputs the [Application](https://docs.unity3d.com/ScriptReference/Application.html)’s path to the Console
> //Run this on the target device to find the application data path for the platform
> using UnityEngine;
> 
> public class Example : [MonoBehaviour](https://docs.unity3d.com/ScriptReference/MonoBehaviour.html)
> {
> string m_Path;
> 
> void Start()
> {
> //Get the path of the Game data folder
> m_Path = Application.dataPath;
> 
> //Output the Game data path to the console
> Debug.Log("dataPath : " + m_Path);
> }
> }
> ```
