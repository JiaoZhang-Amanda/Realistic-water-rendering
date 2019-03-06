# Realistic water rendering

## Introduction

The project is aimed to render the realistic water by implementing the water refraction and reflection.

## Implementation
### The wave generation
* Use a normal map to create a static water ripple.
* Add the G component of each pixel of the normal map and reduced the R and B components, so as to make the water surface fluctuate more vertically
* Use time as a variable in the shader to control the sampling coordinates in each frame.

- R and B represent two directions parallel to the horizontal plane
- G represents the direction perpendicular to the horizontal plane.

The Normal Map Used for Water Surface:
![](https://github.com/JiaoZhang-Amanda/Realistic-water-rendering/raw/master/Project-Photos/The-normal-map)

### The water reflection
* First, get the water reflection view texture by using RenderToTexture (RTT). RTT is used to obtain the reflection view texture by using the projection camera.
* Then, each vertex on the water surface can acquire the UV of the reflection view texture.
* Finally, all UV coordinates are used to mixed the reflection view texture with water surface in the shading stage.

The result of reflection of water:
![](https://github.com/JiaoZhang-Amanda/Realistic-water-rendering/raw/master/Project-Photos/Original "without reflection.")
![](https://github.com/JiaoZhang-Amanda/Realistic-water-rendering/raw/master/Project-Photos/Reflection "with reflection")

### The water refraction
* Generate the corresponding view texture in the same way with reflection view texture.
* Then, the refraction view texture is projected on the water surface so that all vertexes get their sample coordinate.
* Finally, the refraction view texture is mixed with the water surface and the shader can produce the refraction effect .

The result of refraction of water:
![](https://github.com/JiaoZhang-Amanda/Realistic-water-rendering/raw/master/Project-Photos/Water-with-Refraction1 "with refraction")
![](https://github.com/JiaoZhang-Amanda/Realistic-water-rendering/raw/master/Project-Photos/Water-with-Refraction2 "with refraction")

## Performance
The performance of the realistic water rendering is as follow:
![](https://github.com/JiaoZhang-Amanda/Realistic-water-rendering/raw/master/Project-Photos/Result-of-Realistic-water-rendering "Perfomance")

The dynamic display of the rendering:
![](https://github.com/JiaoZhang-Amanda/Realistic-water-rendering/raw/master/Realistic-water-rendering)
