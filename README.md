# Realistic-water-rendering
Render realistic water by implementing the water refraction and reflection

[Simulation water waves]
--Normal mapping
Used the Nvidia normal maps plug-in in PhotoShop to modify the found normal maps, so that they can make the water surface have more roaring waves.
--Moving texture
In order to make the water surface produce dynamic ripple, we need to use a common texture processing technology-moving texture technology. 
We use time as a variable in the shader to control the sampling coordinates in each frame.

[Implementation of reflection]
RenderToTexture (RTT)
Rendering to Texture Technology converts a view of a 3D model into a 2D texture, and render the 2D texture as a rectangular image to the back buffer. 
This technique allows us to dynamically obtain 2D textures of the reflective and refractive views of the water surface in each frame. With these two 2D textures, we can further construct the refractive and reflective maps of the water surface.

[Implementation of refraction]
Reflective texture and refractive texture are essentially the same. The difference is the observation position used to generate the view texture.
