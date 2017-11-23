Based on feedback from ChemicalR I'm cross posting all the things I've bookmarked in reguards to planet rendering here in the code forums. 

[url=http://www.gamasutra.com/view/feature/3098/a_realtime_procedural_universe_.php]Sean O'Neil[/url]'s 4 2001 part series is considered a foundation for realistic large scale (planets on up) rendering. Most of these methods are now obsolete and replaced with faster methods and gpu shaders. His [url=http://http.developer.nvidia.com/GPUGems2/gpugems2_chapter16.html]atmospheric scattering[/url]method is still used often due to its relative simplicity, but it only produces earth atmospheres.

[url=http://acko.net/blog/making-worlds-1-of-spheres-and-cubes/]Steven Wittens[/url] 2009 multipart series is frequently linked to as I've searched for best practices in creating planets using modern methods. It is based on a cube with mesh texture and normalizes the vertex points into a sphere. The advantage to this method is that conventional terrain LOD methods, often used in first person or third person games with vast outdoor scenes, can be used at a planatary scale. A simple normalization will result in a [url=http://i.imgur.com/ss5TwaF.png]bunching of vertexes near the edges[/url]. There is a [url=http://mathproofs.blogspot.com/2005/07/mapping-cube-to-sphere.html]proof[/url] which will normalize the vertex in a way that results in polygons of equal area. Here is my [url=https://bitbucket.org/croxis/planet/src/603fa29c2bf23feb9a31cefc34182f8ba6334a09/planet_surface_vert.glsl?at=default]vertex shader[/url] that demonstrates both methods. [url=https://www.youtube.com/watch?feature=player_embedded&v=ck27Xu5XAJE]Here[/url] is a video of his method creating a small almost-sphere asteroid moon using an adaptive quadtree. Keep in mind that this object is, before shaders, a cube.

At Siggraph 2007 Maxis did [url=http://www.andrewwillmott.com/s2007]several presentations[/url] on the methods they used for spore. They used a [url=https://www.cs.cmu.edu/~ajw/s2007/0251-SphericalWorlds.pdf]brush[/url] [url=http://www.nullpointer.co.uk/content/procedural-planets/]method[/url] to alter the heightmap. I haven't looked too much into this method yet but, combined with a quadtree-based storage system, might be a great way to handle player influences (craters, open pit mining) on a planet.

I bookmarked [url=http://stainlessbeer.weebly.com/planets-1-mercators.html]this[/url] site a while ago. This site has 10 tutorials that focus more on procedural generation of various planet types. My project takes place in our solar system so I have not spent much time looking into procedural generation practices.

Random interlude: How [url=http://simonschreibt.blogspot.de/2013/03/homeworld-backgrounds.html]homeworld[/url] [url=http://simonschreibt.blogspot.de/2013/03/homeworld-2-backgroundstech.html]did[/url] its background.

[url=http://evasion.inrialpes.fr/~Eric.Bruneton/]Eric Bruneton[/url] has published a number of recent (2008-2012) on realistic rendering. One such is a precomputed atmospheric scattering shader which, while more complicated, is an improvement to oneil's. 

[url=http://johnwhigham.blogspot.com/]John Whigham[/url] blog has covered assorted procedural planet generation elements.

[url=http://www.greenleaf.dk/projects/proceduralplanet]Another paper[/url] (2011) 82 pages covering ROAM to river systems. Link to pdf at bottom

[url=http://procworld.blogspot.com/]Miguel Cepero[/url]'s blog coveres the development of his Voxel Farm engine, which is now being used in EQNext. His blog covers procedural generation as well as voxels.

[url=http://proland.inrialpes.fr/]Proland[/url] is a GPL3 "C++/OpenGL library for the real-time realistic rendering of very large and detailed 3D natural scenes on GPU"

There is another site in german with a lot of tutorials on procedural planets. Alas I could not find it.


[url=http://www.sperlhofer.com/images/stories/atmospheric/thesis-sperlhofer.pdf]Here[/url] is a thesis that helps explains bruneton's atmosphere scattering method. [url=https://www.youtube.com/watch?v=GmVKyp1APhY]Video[/url]

[url=http://vterrain.org]VTerrain[/url] contains links to a lot of sources on real time terrain rendering.
