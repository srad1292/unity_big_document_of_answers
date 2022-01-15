# Move a kinematic object

Kinematic rigidbody is useful for things like an obstacle moving across the screen that the player will need to dodge.  To move the object all you need to do is set the velocity in the update using a vector that contains x move speed and y move speed.  As an example to move an object from left to right across the screen

```c#
void Update()
    {
        if(xMoveSpeed > Mathf.Epsilon) {
            myRigidBody.velocity = new Vector2(xMoveSpeed, 0f);
        }
    }
```

---
Back Links

* [Movement](../0_movement.md)