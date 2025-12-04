# Y-Sorting in 2D Games
In the 3D world, the graphics card uses a "Depth Buffer" (Z-buffer) to calculate which pixel is closest to the camera. In 2D games (like Stardew Valley, Zelda: A Link to the Past, or Among Us), we don't have a Z-buffer. We are painting on a flat canvas.

To create the illusion of depth, we use the Painter's Algorithm: We paint the furthest objects first, and the closest objects last.

But how do we know what is "closer"?

## The Y-Axis Rule
In a Top-Down or Isometric view, the Y-axis represents depth.

 - Low Y Value (Top of screen): Far away.

 - High Y Value (Bottom of screen): Close to camera.

Therefore, we simply need to draw objects with a lower Y value before objects with a higher Y value.

## The Secret: The Pivot Point
A common mistake beginners make is sorting by the y position of the sprite's top-left corner (the default x,y in most engines).

This is wrong. You must sort by the feet of the object.

If you sort by the top of the sprite, a tall tree and a short bush at the same depth will be drawn in the wrong order. You must compare where the object touches the ground.
