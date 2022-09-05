# Scene Transition

I will start off with a simple Fade In / Out Animation

Create a new Game Object and call it your Scene Loader.  
Add a SceneLoader script to it.  
Add a canvas to the Scene Loader, call it fader or something similar and set the "UI Scale Mode" to "Scale With Screen Size".  
Add an image to the canvas, set the color, and scale it to cover the screen.    
If you have other canvases in the scene, you may need to update the sorting order of your canvas.  
Select your canvas in the heirarchy, go to the animation panel, and create a new animation.  
In your animation, record and set keyframe 1 to alpha of 0%, go the duration of animation you want ahead, and set the alpha to 100%.  
This will be the fade_out animation.  
Create a new clip, copy in the keyframes from the other clip, and reverse the order.  
This will be the fade_in animation.  
For both animations, uncheck the "loop time" flag.  
In the animator, set the entry state to go to fade_in.  
Create another transition between fade_in and fade_out.  
Add a trigger parameter to the clip and add it to the transition between fade_in and fade_out.  
Turn off the 'Exit Time' settings for the transition and set transition duration to 0.  
Add a serialized field to the SceneLoader script and set it to the animator(in the canvas).  
When you want to load a screen, start a coroutine and call an enumerator that, triggers the parameter, waits for some time, and then loads the next scene.  
The way this works is scene loads, fade in, on scene transition, we fade out which sets screen to black.  Then the next scene loads and the entry animation goes to the fade_in state, completing the animation.


---
Back Links

* [Errors](../0_animation.md)