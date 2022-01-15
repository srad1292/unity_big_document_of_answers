# Setup Input System Package

1. Open the Unity Package Manager and add the "Input System" package to the project
2. On your player prefab, add the "Player Input" component
3. Press the "Create Actions" button to setup a .inputactions file where you will start with some default key bindings that you can add to or remove.
4. Also, inside the "Player Input" component press the "Open Input Settings" button and then "Create Settings Asset" and save it to get an inputsettings.asset file.
5. You may need to go to your Event System and under the "Standalone Input Module" and press the button that switches to new system.
6. You can then add handlers for the actions within the scripts on that prefab.  For example if you have a MoveLeft keybinding you can do

```c#
void OnMoveLeft(InputValue value) {
    Vector2 inputVelocity = value.Get<Vector2>();
}
```

---
Back Links

* [Movement](../0_movement.md)