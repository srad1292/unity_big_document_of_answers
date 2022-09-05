# X Hides Inherited Member

I have seen this warning and the reasoning behind the times I have seen it is that I am
trying to create a property on a Monobehavior that already exists. For example,

```c#
SpriteRenderer renderer;
```

Monobehavior game object with a sprite renderer will have a property called renderer already
so you will need to name the property something else in your script.

---
Back Links

* [Errors](../0_errors.md)