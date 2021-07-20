# OpenGL Demo Scene Technical Document


## Introduction

As part of the 5300 module we have to create a 3D demo scene with OpenGL using computer graphics techniques.
To do this demo scene I follow courses of my teachers Elias Farhan and Frederic Dubouchet and tutorials from [learnopengl.com](https://learnopengl.com).

## Scene

My scene consist of an spatial library of objects where a objects with differents techniques of graphics techniques. The camera start at a position to see meteors and go front of the different objects each 10 seconds.
Among present objects there are a hourglass, a cube, a F1 car and meteors.

![](https://worgaros.github.io/Images/openwin.gif)

## Implementation

### Model Loading

Objects are .obj with their materials files. They are loaded with Assimp a library to load 3D models.
Textures are images .png or .jpg. They are loaded with stb a library to load images.

Assimp load each mesh to then be able to display them.
stb load the images whose path is specified in the .mtl of .obj.

### Lighting

The ligthing technique applied to the models in the shaders is the Blinn phong method.
It use ambient, diffuse and specular values to simulate lighting.
It is not physically realistic but it gives a proper result for a simple demo scene.

Textures are given to shaders and included in values of ambiant, diffuse and specular.

### Blending

To do my transparency houglass I use blending. It's a OpenGL functionality that allows to blend colors using the alpha value.



### Normal Mapping

Normal mapping allows models to use a normal map texture in addition to diffuse and specular textures.
The positions are calculated in tangent space instead of world space using TBN matrix who do the changement of space.
Normals are extracted from the normal map, assimp can directly extact tangent and bitangent.



### Stencil Buffer



### Instancing



## Conclusion

### [Back to main page](https://worgaros.github.io/)