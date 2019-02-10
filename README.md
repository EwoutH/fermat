# Fermat [![AppVeyor Build Status](https://ci.appveyor.com/api/projects/status/github/OpenVisualCloud/SVT-AV1?branch=master&svg=true)](https://ci.appveyor.com/project/OpenVisualCloud/SVT-AV1)

Fermat 2.0 is a CUDA physically based research renderer designed and developed by Jacopo Pantaleoni at NVIDIA.
Its purpose is mostly educational: it is primarily intended to teach how to write rendering algorithms,
ranging from simple forward path tracing, to bidirectional path tracing, to Metropolis light transport with many
of its variants, and do so on massively parallel hardware.

The choice of CUDA C++ has been made for various reasons: the first was to allow the highest level of expression and
flexibility in terms of programmability (for example, with template based meta-programming); the second was perhaps
historical: when Fermat's development was started, other ray tracing platforms like Microsoft DXR did not yet exist.
The ray tracing core employed by Fermat is OptiX 6.0 - though future versions might also add a DXR or VKRT backend.

Fermat is built on top of another library co-developed for this project: CUGAR - CUDA Graphics AcceleratoR.
This is a template library of low-level graphics tools, including algorithms for BVH, Kd-tree and octree construction,
sphericals harmonics, sampling, and so on and so on.
While packaged together, CUGAR can be thought of a separate educational project by itself.
More information can be found in the relevant Doxygen documentation.

The official project page can be found here:
https://nvlabs.github.io/fermat/

## Dependencies

Fermat has the following dependencies:

 - cub         : contained in the package
 - freeglut    : contained in the package
 - Assimp      : contained in the package
 - CUDA 10.0   : not contained - it should be separately downloaded and installed on the system
 - OptiX 6.0   : not contained - it should be separately downloaded and copied in the folder contrib/OptiX

Its distribution also contains a set of adapted models originally taken from Benedikt Bitterli's rendering resources:
https://benedikt-bitterli.me/resources.
 
## Compilation

Once all dependencies are sorted out, the Visual Studio 2015 solution file vs/fermat/fermat.sln can be opened
and the project can be compiled.

Pre-compiled 64-bits Windows build are generated with [AppVeyor](https://ci.appveyor.com/project/NVlabs/fermat) and deployed to GitHub Releases on [tagged commits](https://github.com/NVlabs/fermat/tags).

## Use

After compilation, you can launch Fermat's path tracer with the following command line:
fermat.exe -view -pt -r 1600 900 -i ../../models/bathroom2/bathroom.fa
