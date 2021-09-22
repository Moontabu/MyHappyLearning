⦁	Ambient Occlusion
Ambient occlusion is a grayscale texture that specifies how exposed each pixel is to ambient lighting. The darker the value the less light it receives. It is a quite simple technique and tends to give great results.

The following texture is the ambient occlusion map for the rock wall example:
 
F 2.5 Ambient occlusion sample

As we can see in the rock cracks the occlusion value is darker, so light will be less effective there.

⦁	Roughness/ Glossiness map
Roughness maps are grayscale images that specify the irregularities of each pixel, so determines the light deviation that certain pixel would have. The greater the value the rougher the surface will be. In the case of the rock the whole texture will be white, since rocks are rough.


⦁	Metallic map
Metallic textures are grayscale images that specify the metalness of each pixel, the greater the value the more metallic it will be. In the example of the rock the texture would be filled with black, again the good practice in this case is to use a single value to specify the metalness, this way we avoid having too many textures in the GPU.


⦁	Grayscale Images
A grayscale image is such image where the Red, Green,Blue and alpha channels hold the same number. So theoretically we do not need all the channels to hold that information, one single channel is able to carry all the information needed. We can take advantage of this situation by combining different grayscale images in a single one. For example, we can join the metallic map, the ambient occlusion map, the heightmap and the specular map in a

single image giving to each channel the value of each one of the maps. This way we can have only one texture loaded instead of four.

Recently Unity released a new rendering pipeline and changed most of the materials that were used previously. Most of them uses this technique to optimize the usage of the GPU.


⦁	Procedural Content Generation

⦁	Introduction to PCG
Procedural content generation(PCG)[5] in video games is any content that has been produced by the computer through an algorithm. It has many applications besides video games, but the following are some of the applications and benefits in video games:

⦁	Replayability: Using procedural generation we can create infinite levels, a game that generate dungeons procedurally will offer a different experience any time we play. Games like “Diablo” or “Rogue” started using this techniques.
⦁	Terrain creation: As explained previously we can generate heightmaps procedurally and use them to create terrains, this way the process is automatic. We can also compute the height value of the terrain at runtime and create an infinite terrain. Games like “No man’s sky” uses this technique.
⦁	Optimize memory usage: Following the previous example, computing things like terrain data at runtime, it will also minimize the memory usage since we won’t need to store that anywhere.
⦁	Speed up design process: We can also place assets procedurally, for example grass, trees, houses, … Or even generate cities procedurally. There is no need to mention the time that could be saved using this techniques.
⦁	Texture generation: We can generate textures procedurally by combining noises and filters to generate PBR textures. One of its main strength is that since it is calculated through an algorithm, procedural textures are resolution independent. They will not lose detail when scaling them. They are also really customizable since a change of one parameter can dramatically change the final result.
