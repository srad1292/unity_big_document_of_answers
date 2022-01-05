# Rotate Sprite

As an example we will flip on the X axis. To flip, we simply need to set the X value of the scale vector for the object's transform.  

```c#
transform.localScale = new Vector2(transform.localScale.x * -1, 1f);
```

As an example we will have a moving sprite and when the sprite exits a trigger collider(the ground for example) we can do the following.  

1. Flip their horizontal velocity
2. Set the transform scale to opposite sign

```c#
Float moveSpeed = myRigidBody.velocity.x;
myRigidBody.velocity = new Vector2(-1 * moveSpeed, 0f);
transform.localScale = new Vector2(transform.localScale.x * -1, 1f);
```

---
Back Links

* [Sprites](../0_sprites.md)
