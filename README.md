# OptiX-PathTracer-Basic-High-Quality-Rendering
Rendering results for [UCSD CSE 168 Rendering](http://cseweb.ucsd.edu/~viscomp/classes/cse168/sp20/168.html) final project. :+1:

### List of tasks. 
- [x] Refraction
- [x] Environment Mapping
- [x] Support .obj Files
- [x] Video for Demo

## Refraction
- Implement dielectric material for refraction as following commands:
 ```
 dielectric <ior>
 ```
 where ior indicates index of refraction. In dielectric layer, I consider the internel total reflection and the Fresnel equation for sampling the reflections and refractions.
 
Cornell Dielectric 1       | Cosine Dielectric 2
:-------------------------:|:--------------------------:
![](https://github.com/yuyingyeh/OptiX-PathTracer-Basic-High-Quality-Rendering/blob/master/img/cornellDielectric.png)  |  ![](https://github.com/yuyingyeh/OptiX-PathTracer-Basic-High-Quality-Rendering/blob/master/img/cornellDielectric2.png)

## Enviroment Mapping
- Implement environment mapping as following commands:
 ```
 envmap <pathToHDRImages>
 ```
 where `pathToHDRImages` indicates HDR image file path. I use HDR images downloaded from [HDRIHaven](https://hdrihaven.com/hdris/). I use the library `HDRLoader.h` provided under `sutil/`  as my HDR image loader to get a `Texture Sampler` and look up the background values using `tex2D` via `(u,v)` coordinates given the ray directions in `miss program`. I refer to the [OptiX Tutorial](https://raytracing-docs.nvidia.com/optix6/tutorials_6_5/optix_tutorials.191212.A4.pdf) to implement this method.

## Support .obj Files
- Implement a method to read .obj file to the renderer. 
 ```
 obj <pathToObjFiles>
 ```
where `pathToObjFiles` incidates `.obj` file path. I use external library [`tinyobjloader/tiny_obj_loader.h`](https://github.com/tinyobjloader/tinyobjloader/tree/v0.9.x) to fetch faces and vertices and store the triangles following the previous method. I follow the [example code](https://github.com/tinyobjloader/tinyobjloader/blob/v0.9.x/README.md) provided in the library repository to fetch the triangles.

## Video for Demo
For each environment map, I rendered two scenes: 1) Glass Sphere in Environment Map 2) Glass [Bunny](https://graphics.stanford.edu/~mdfisher/Data/Meshes/bunny.obj) in Environment Map.

- Environment map : [Cayley Interior](https://hdrihaven.com/hdri/?c=indoor&h=cayley_interior)
<img src="https://hdrihaven.com/files/hdri_images/tonemapped/1500/cayley_interior.jpg" width="720" height="360">

Glass Sphere in Enviroment Map | Glass Bunny in Environment Map
:-------------------------:|:--------------------------:
![](https://github.com/yuyingyeh/OptiX-PathTracer-Basic-High-Quality-Rendering/blob/master/video/videoEnv.gif)  | ![](https://github.com/yuyingyeh/OptiX-PathTracer-Basic-High-Quality-Rendering/blob/master/video/videoEnvBunny.gif)

- Environment map : [Palermo Sidewalk](https://hdrihaven.com/hdri/?h=palermo_sidewalk)
<img src="https://hdrihaven.com/files/hdri_images/tonemapped/1500/palermo_sidewalk.jpg" width="720" height="360">

Glass Sphere in Environment Map | Glass Bunny in Environment Map
:-------------------------:|:--------------------------:
![](https://github.com/yuyingyeh/OptiX-PathTracer-Basic-High-Quality-Rendering/blob/master/video/videoEnv2.gif)  | ![](https://github.com/yuyingyeh/OptiX-PathTracer-Basic-High-Quality-Rendering/blob/master/video/videoEnv2Bunny.gif)
