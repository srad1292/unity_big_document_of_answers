# How to use a custom sprite for a particle effect

There are multiple ways to handle this depending on what you want to accomplish.

## 1. Particle effect with animation from sprites

In your particle system, go to the texture sheet animation system and change the mode from grid to sprites.  Add a dropdown for each sprite in the sprite sheet and then fill each one with the appropriate sprite.  Play around with the time mode and related values to get the animation timing the way you want.

## 2. Single custom sprite with no animation

You can create a material with something like Unlit/Texture as the shared and set the sprite to be your custom sprite. Then in your particle system renderer system, you can use your new material as the material for the renderer.  

## 3. Random emission between multiple sprite options

To do this, you either need multiple particle systems or you need to have a texture that has the different sprites on it.  Assuming you have a texture with the different sprites, you can follow the same procedure as the first section.  Once you have it setup, change the time mode to "Lifetime" and then in the "Frame over time" section, press the dropdown and choose random between two constants.  This will choose one of the sprites at random to emit.

---
Back Links

* [Visual Effects](..\0_visual_effects.md)