#todo #unity #cSharp [[Serialization]]

## Serializar y deserializar
### JsonUtility
Viene incluido por defecto en Unity.
JsonUtility es una clase que permite serializar y deserializar Unity Objects en JSON.

#### Como utilizar JsonUtility
1. Creamos una clase o struct para describir los datos que necesitamos serializar.
   
```csharp
[Serializable]
public class MyClass
{
    public int level;
    public float timeElapsed;
    public string playerName;
}
```

```csharp
MyClass myObject = new MyClass();
myObject.level = 1;
myObject.timeElapsed = 47.5f;
myObject.playerName = "Dr Charles Francis";
```


2. Usamos el metodo `JsonUtility.ToJson(Object)` para serializar los datos a Json.

```csharp
string json = JsonUtility.ToJson(myObject);
	// json now contains: '{"level":1,"timeElapsed":47.5,"playerName":"Dr Charles Francis"}'
```


3. Utilizamos el método `JsonUtility.FromJson<Object>(string)` para deserializar los datos de un Json.
   
```csharp
myObject = JsonUtility.FromJson<MyClass>(json);
```


