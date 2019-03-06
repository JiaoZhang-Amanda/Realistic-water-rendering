# Realistic water rendering

## Introduction

The project is aimed to render the realistic water by implementing the water refraction and reflection.

## Implementation
### The wave generation
* Use a normal map to create a static water ripple.
* Add the G component of each pixel of the normal map and reduced the R and B components, so as to make the water surface fluctuate more vertically
* Use time as a variable in the shader to control the sampling coordinates in each frame.

R and B represent two directions parallel to the horizontal plane<br>
G represents the direction perpendicular to the horizontal plane.

The Normal Map Used for Water Surface:
<br><img height="300" src="https://github.com/JiaoZhang-Amanda/Realistic-water-rendering/raw/master/Project%20Photos/The%20normal%20map.jpg"/><br>

### The water reflection
* First, get the water reflection view texture by using RenderToTexture (RTT). RTT is used to obtain the reflection view texture by using the projection camera.
* Then, each vertex on the water surface can acquire the UV of the reflection view texture.
* Finally, all UV coordinates are used to mixed the reflection view texture with water surface in the shading stage.

The result of reflection of water:<br>
<img height="300" src="https://github.com/JiaoZhang-Amanda/Realistic-water-rendering/raw/master/Project%20Photos/Original.jpg"/><br>
<img height="300" src="https://github.com/JiaoZhang-Amanda/Realistic-water-rendering/raw/master/Project%20Photos/Reflection.jpg"/>

### The water refraction
* Generate the corresponding view texture in the same way with reflection view texture.
* Then, the refraction view texture is projected on the water surface so that all vertexes get their sample coordinate.
* Finally, the refraction view texture is mixed with the water surface and the shader can produce the refraction effect .

The result of refraction of water:<br>
<img height="300" src="https://github.com/JiaoZhang-Amanda/Realistic-water-rendering/raw/master/Project%20Photos/Water%20with%20Refraction1.jpg"/><br>
<img height="300" src="https://github.com/JiaoZhang-Amanda/Realistic-water-rendering/raw/master/Project%20Photos/Water%20with%20Refraction2.jpg"/>

## Performance
The performance of the realistic water rendering is as follow:<br>
<img height="300" src="https://github.com/JiaoZhang-Amanda/Realistic-water-rendering/raw/master/Project%20Photos/Result%20of%20Realistic%20water%20rendering.jpg"/>

The dynamic display of the rendering:
![](https://github.com/JiaoZhang-Amanda/Realistic-water-rendering/raw/master/Project%20Photos/Dynamic%20Performance.gif)
