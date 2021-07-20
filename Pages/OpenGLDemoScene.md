# OpenGL Demo Scene Technical Document


## Introduction

As part of the 5300 module we have to create a 3D demo scene with OpenGL using computer graphics techniques.
To do this demo scene I follow courses of my teachers Elias Farhan and Frederic Dubouchet and tutorials from [learnopengl.com](https://learnopengl.com).

## Scene

My scene consist of an spatial library of objects with different techniques of graphics techniques. The camera start at a position to see meteors and go front of the different objects each 10 seconds.
Among present objects there are a hourglass, a cube, a F1 car and meteors.

![](https://worgaros.github.io/Images/openglscene.gif)

## Implementation

### Model Loading

Objects are .obj with their materials files. They are loaded with Assimp a library to load 3D models.
Textures are images .png or .jpg. They are loaded with stb a library to load images.

Assimp load each mesh to then be able to display them.
stb load the images whose path is specified in the .mtl of .obj.

![](https://worgaros.github.io/Images/openwin.gif)

### Lighting

The ligthing technique applied to the models in shaders is the Blinn phong method.
It use ambient, diffuse and specular values to simulate lighting.
It is not physically realistic but it gives a nice result for a simple demo scene.

Textures are given to shaders and included in values of ambiant, diffuse and specular.

![](https://worgaros.github.io/Images/openwin.gif)

### Blending

To do my transparency hourglass I use blending. It's a OpenGL functionality that allows to blend colors using the alpha value.

![](https://worgaros.github.io/Images/blending.PNG)

### Normal Mapping

To do my cube I use normal mapping.
Normal mapping allows models to use a normal map texture in addition to diffuse and specular textures.
The positions are calculated in tangent space instead of world space using TBN matrix who do the changement of space.
Normals are extracted from the normal map, assimp can directly extract tangent and bi-tangent to calcul TBN matrix.

![](https://worgaros.github.io/Images/openwin.gif)
![](https://worgaros.github.io/Images/normal.PNG)

### Stencil Buffer

To do my F1 car outline I use the stencil buffer.
With the stencil buffer we use stencil mask to draw outlines around mesh by redrawing our mesh scale up, but with a unified color and without overriding the original mesh.

![](https://worgaros.github.io/Images/stencilbuffer.PNG)

### Skybox

To do the background of my scene I use a cubemap.
Cubemap is a graphic technique that gives the illusion that a three-dimensional space is infinite around you. 
We use textures for each side of the cube.

![](https://worgaros.github.io/Images/openwin.gif)

## Optimisation

### Instancing

To do my meteors I use instancing.
Instancing is a method the draw the same model lots of times with just one draw call because all of their datas have already been loaded to the gpu.
It's very important when we draw hundreds or thousands of times the same model.

![](https://worgaros.github.io/Images/instancing.PNG)

## Conclusion
I am happy to have learned a lot of computer graphics methods but I am not completely satisfied because if I have more time and especially if I will be able to manage my stress so as not to waste days having stress crises I could have added:

- Frustum culling to don't draw object outside of the camera view.
- Shadow map to use it with new object for the space library
- PBR to have more realistic textures.
- A camera with more complex movements like a camera that moves forward and turns, which does not just teleport.
- Sounds to have a more alive scene feeling.

### [Back to main page](https://worgaros.github.io/)