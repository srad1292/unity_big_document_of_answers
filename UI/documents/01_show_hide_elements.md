# Show and Hide Elements

One way you can show/hide elements is by using the SetActive method on the element

```c#
[SerializeField] GameObject element;

HideElement() {
    element.SetActive(false);
}

ShowElement() {
    element.SetActive(true);
}
```

---
Back Links

* [UI](../0_ui.md)
* [Game Objects](../../Game_Objects/0_game_objects.md)
