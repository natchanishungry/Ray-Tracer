# Ray-Tracer
Created Ray Tracer using Java OpenGL that implements Perlin Noise, Motion Blur, Mirror Reflection, Soft Shadows, and more.  

Within a4data, there are the XML files that contain descriptions of 3D scenes. Each file is organized as a sequence of named materials, lights, cameras, nodes, and geometry. The main scene is defined in the top-level node. The scene nodes each have an associated transformation. The node definition can contain transformation attributes: translation, rotation, and scale. Finally, each node can also contain a list of child nodes, allowing a hierarchy of transformations and geometry to be built. Parser.java, the code that parses the XML, was mostly written by my professor Paul Kry, although I did make many adjustments to it as I went along.

***What I worked on directly***:

**Scene.java**

The scene class which contains information about all the intersectable objects, the lights, and extra scene information such as the ambient light. This is where the rendering nested for loop lives.

Also: the code for generating a ray to intersect with the scene, lighting and shading, soft shadows, motion blur, supersampling, mirror reflection, fresnel reflection and refraction all lives here. 

**Sphere.java / Plane.java / Box.java / Mesh.java**

These are all subclasses of Intersectable. Each have extra information relevant to the object type, such as radius and center for Sphere. I implemented the intersection code for each!

**SceneNode.java**

Each scene node has a transform matrix to allow you to re-position and re-orientate objects within your scene. The transformations defined in the scene nodes transform the rays before intersecting the geometry and child nodes, then transform the normal of the intersection result returned to the caller. The code in the SceneNode class implements the Intersectable interface and performs the intersection test on all of its child nodes.

**PerlinNoise.java**

I implemented a noise calculation for the closest point of intersection with a box or sphere. 



*Here are some cool images that show my results*:

Cornell:

![Test Image](https://github.com/natchanishungry/Ray-Tracer/blob/master/PHOTOS/Cornell.png)

Box Stacks: 

![Test Image](https://github.com/natchanishungry/Ray-Tracer/blob/master/PHOTOS/BoxStacks.png)

Torus Mesh:

![Test Image](https://github.com/natchanishungry/Ray-Tracer/blob/master/PHOTOS/TorusMesh.png)

Two Spheres on a Plane (with some supersampling):

![Test Image](https://github.com/natchanishungry/Ray-Tracer/blob/master/PHOTOS/TwoSpheresPlane.png)

Weird Scene with Perlin, Mirror, Refraction, Motion Blur, Soft Shadow... :

![Test Image](https://github.com/natchanishungry/Ray-Tracer/blob/master/PHOTOS/FinalScene.png)

An Experiment with Perlin Noise:

![Test Image](https://github.com/natchanishungry/Ray-Tracer/blob/master/PHOTOS/perlinNoise.png)


