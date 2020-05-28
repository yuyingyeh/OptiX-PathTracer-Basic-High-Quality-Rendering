# OptiX-PathTracer-Basic-High-Quality-Rendering
Milestone rendering results for [UCSD CSE 168 Rendering](http://cseweb.ucsd.edu/~viscomp/classes/cse168/sp20/168.html) final project.

### List of tasks TODO.
- [x] Refraction
- [ ] Environment Mapping
- [ ] Two Add-ons
- [ ] Video for Demo

## Refraction
- Implement dielectric material for refraction as following commands:
 ```
 dielectric <ior>
 ```
 where ior indicates index of refraction. In dielectric layer, I consider the internel total reflection and the Fresnel equation for sampling the reflections and refractions.
 
Cornell Dielectric 1       | Cosine Dielectric 2
:-------------------------:|:--------------------------:
![](https://github.com/yuyingyeh/OptiX-PathTracer-Basic-High-Quality-Rendering/blob/master/img/cornellDielectric.png)  |  ![](https://github.com/yuyingyeh/OptiX-PathTracer-Basic-High-Quality-Rendering/blob/master/img/cornellDielectric2.png)
