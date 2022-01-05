# Sprite direction based on movement

To face sprite in the correct direction based on movement, we will store a Vector2 for player input and use the sign of the X velocity from said Vector2 to ensure the sprite is facing the correct direction.

```c#
// Property to hold player movement vector
Vector2 moveInput;

// Update the vector when move input fires
void OnMove(InputValue value) {
    if(!canMove) { return; }
    moveInput = value.Get<Vector2>();
}

//Handle the sprite direction(either call from Update or the movement handlers)
void FlipSprite() {
    // Floats can be wonky and to handle rounding errors where very small numbers are not counted as 0, we will use Mathf.Epsilon instead of 0 for velocity check.
    bool playerHasHorizontalSpeed = Mathf.Abs(myRigidBody.velocity.x) > Mathf.Epsilon;
    if(playerHasHorizontalSpeed) {
        //Mathf.Sign returns -1 or 1 based on if value is negative or 0+ so we can set the scale of the transform based on that to be facing the proper direction
        transform.localScale = new Vector2(Mathf.Sign(myRigidBody.velocity.x), 1f);
    }
}
```

---
Back Links

* [Movement](../0_movement.md)
* [Sprites](../../Sprites/0_sprites.md)