Based on feedback from ChemicalR I'm cross posting all the things I've bookmarked in reguards to planet rendering here in the code forums. 

[Sean O'Neil](http://www.gamasutra.com/view/feature/3098/a_realtime_procedural_universe_.php)'s 4 2001 part series is considered a foundation for realistic large scale (planets on up) rendering. Most of these methods are now obsolete and replaced with faster methods and gpu shaders. His [atmospheric scattering](http://http.developer.nvidia.com/GPUGems2/gpugems2_chapter16.html) method is still used often due to its relative simplicity, but it only produces earth atmospheres.

[Steven Wittens](http://acko.net/blog/making-worlds-1-of-spheres-and-cubes/) 2009 multipart series is frequently linked to as I've searched for best practices in creating planets using modern methods. It is based on a cube with mesh texture and normalizes the vertex points into a sphere. The advantage to this method is that conventional terrain LOD methods, often used in first person or third person games with vast outdoor scenes, can be used at a planatary scale. A simple normalization will result in a [bunching of vertexes near the edges](http://i.imgur.com/ss5TwaF.png). There is a [proof](http://mathproofs.blogspot.com/2005/07/mapping-cube-to-sphere.html) which will normalize the vertex in a way that results in polygons of equal area. Here is my [vertex shader](https://bitbucket.org/croxis/planet/src/603fa29c2bf23feb9a31cefc34182f8ba6334a09/planet_surface_vert.glsl?at=default) that demonstrates both methods. [Here](https://www.youtube.com/watch?feature=player_embedded&v=ck27Xu5XAJE) is a video of his method creating a small almost-sphere asteroid moon using an adaptive quadtree. Keep in mind that this object is, before shaders, a cube.

At Siggraph 2007 Maxis did [several presentations](http://www.andrewwillmott.com/s2007) on the methods they used for spore. They used a [brush](https://www.cs.cmu.edu/~ajw/s2007/0251-SphericalWorlds.pdf) [method](http://www.nullpointer.co.uk/content/procedural-planets/) to alter the heightmap. I haven't looked too much into this method yet but, combined with a quadtree-based storage system, might be a great way to handle player influences (craters, open pit mining) on a planet.

I bookmarked [this](http://stainlessbeer.weebly.com/planets-1-mercators.html) site a while ago. This site has 10 tutorials that focus more on procedural generation of various planet types. My project takes place in our solar system so I have not spent much time looking into procedural generation practices.

Random interlude: How [homeworld] (http://simonschreibt.blogspot.de/2013/03/homeworld-backgrounds.html) [did](http://simonschreibt.blogspot.de/2013/03/homeworld-2-backgroundstech.html) its background.

[Eric Bruneton](http://evasion.inrialpes.fr/)Eric.Bruneton/) has published a number of recent (2008-2012) on realistic rendering. One such is a precomputed atmospheric scattering shader which, while more complicated, is an improvement to oneil's. 

[John Whigham](http://johnwhigham.blogspot.com/) blog has covered assorted procedural planet generation elements.

[Another paper](http://www.greenleaf.dk/projects/proceduralplanet) [2011] 82 pages covering ROAM to river systems. Link to pdf at bottom

[Miguel Cepero](http://procworld.blogspot.com/)'s blog coveres the development of his Voxel Farm engine, which is now being used in EQNext. His blog covers procedural generation as well as voxels.

[Proland](http://proland.inrialpes.fr/) is a GPL3 "C++/OpenGL library for the real-time realistic rendering of very large and detailed 3D natural scenes on GPU"

There is another site in german with a lot of tutorials on procedural planets. Alas I could not find it.


[Here](http://www.sperlhofer.com/images/stories/atmospheric/thesis-sperlhofer.pdf) is a thesis that helps explains bruneton's atmosphere scattering method. [Video](https://www.youtube.com/watch?v=GmVKyp1APhY)

[VTerrain](http://vterrain.org) contains links to a lot of sources on real time terrain rendering.
