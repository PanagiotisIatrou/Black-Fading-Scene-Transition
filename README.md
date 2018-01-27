# Black-Fading-Scene-Transition
Change from scene to scene with a smooth black fade effect!

# How to implement:
1) Import the BlackFader.unitypackage in your Unity project
2) Drag the BlackFaderManager prefab to ONLY one scene (usually the first that's loaded)
3) Done!

# How to use:
You just call the GoToScene method located at BlackFader.cs

There are 2 overloads:

```csharp
static public void GoToScene(string sceneName, LoadSceneMode mode, float time);
```
```csharp
static public void GoToScene(string sceneName, LoadSceneMode mode, float time, Action actionAfterArriving, Action actionAfterFinishing);
```

# Examples:

1)
```csharp
// Closes all other scenes and loads MyDestinationScene scene inside 4 seconds in total

private void Start()
{
    BlackFader.GoToScene("MyDestinationScene", UnityEngine.SceneManagement.LoadSceneMode.Single, 2f);
}
```

2)
```csharp
// Closes all other scenes and loads MyDestinationScene scene inside 4 seconds in total.
// It also executes atLoading() when MyDestinationScene is loaded and atFinish()
// when the transition is fully complete

private void Start()
{
    BlackFader.GoToScene("second", UnityEngine.SceneManagement.LoadSceneMode.Single, 2f, atLoading, atFinish);
}

private void atLoading()
{
    Debug.Log("just loaded scene!");
}

private void atFinish()
{
    Debug.Log("now its completely unblacked!");
}
```
