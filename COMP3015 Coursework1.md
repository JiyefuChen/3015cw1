------

Github link：

youtube link：https://youtu.be/-F6OA2LBTCg

## 1. Which version Visual Studio and Operating System you used to test/write the code  locally?

I am using vs2022. The OpenGL version is 4.6.0

## 2. How does it work? o How does your code fit together and how should a programmer  navigate it (not intended to be an exercise in formally documenting the code)? 



To initialize the OpenGL environment and Windows:

Create and manage application Windows using the GLFW library, and load OpenGL functions using GLAD.
Initializes a Window object, mainWindow, and sets the window size and other properties.
Load and prepare resources:

Load shader programs (such as basic render shaders, shadow mapping shaders, etc.).
Load 3D models and textures, prepare light objects (directional light, point light) and material properties.
Set camera parameters and define viewing and projection matrices.
Render loop:

In each frame, input is processed, camera perspective and position updated, and other possible dynamic scene elements.
Execute the shadow mapping rendering pass to generate shadow mapping for the light source.
Render scenes, including 3D models and sky boxes, applying textures, lighting and shadow effects.
Swap buffers and update window contents to show the latest rendered frame.
How do programmers manipulate it
Environment configuration:

Make sure you have all the necessary libraries and dependencies installed (GLFW, GLAD, GLM, etc.).



The w key moves the view forward
The s button shifts the viewing Angle backwards
The a key shifts the viewing Angle to the left
The d key shifts the viewing Angle to the right
The o and p keys drive the frame forward and backward

## 3. Anything else which will help us to understand how your prototype works. 

Core component
GLFW & GLAD:

GLFW is used to create Windows, process user input (keyboard, mouse, etc.), and manage other window-related tasks.
GLAD is used to load and bind OpenGL function Pointers and is one of the standard initialization steps for OpenGL applications.
Shader Program:

Shader program consists of vertex shader and slice shader, which deal with the rendering of vertex data and pixel colors of graphics respectively.
The shader code is loaded and compiled through the CreateShaders function, which is then applied during the rendering process to determine the appearance of each object in the scene.
Camera & Projection:

The camera controls the viewpoint and direction, which determines the Angle and position of the scene to be observed.
The projection matrix defines the visual cone (field of view) and determines which parts of the scene will be rendered on screen.
Lighting & Shadows:

The lighting effect is calculated using a lighting model implemented in the shader, including ambient lighting, diffuse reflection, and specular highlights.
Shading is achieved by rendering shadow maps, which render the scene from the perspective of the light source and then use these maps to determine whether the surface is illuminated by the light source during the actual rendering.
Textures & Materials:

Texture adds detail to the surface of an object, such as the texture of a brick wall, the soil of the ground, etc.
The material defines the properties of the object to reflect light, such as gloss, reflectivity, and so on.