⦁ 技术水平  

<!--⦁	State of the Art-->  

⦁物理基础渲染  

<!--⦁	PBR-->   

在讨论程序纹理之前，重要的是要理解我们将生成哪种纹理，在这种情况下，我们将生成PBR(物理基础渲染)所需的所有纹理。  

<!--Before talking about procedural textures it is important to understand which kind of textures are we going to generate, in this case we are going to generate all the textures needed for PBR (Physically Based Rendering).-->  

根据维基百科，PBR是计算机图形学的一种哲学，旨在以一种更准确地模拟现实世界中的光流的方式来渲染图形，具有客观的照片真实感。  

<!--According to Wikipedia, PBR is a philosophy in computer graphics that seeks to render graphics in a way that more accurately models the flow of light in the real world, having as objective photorealism. -->

做到几个纹理被同时使用，但是在着色器里面又用不同的途径。。

<!--In order to do so several textures are used, each one interpreted in a different way inside the shader.  -->

⦁ 漫反射纹理   

<!--⦁	Diffuse texture-->    

漫反射纹理也用于非pbr纹理。是保存3D对象的原始颜色数据的纹理。基本上它是一个2D文件，使用UV映射包裹着一个3D模型。  

<!--The diffuse texture was also used in non-PBR texturing. Is the texture that holds raw color data of 3D objects. Basically it is a 2D file that is wrapped around a 3D model using UV mapping. --> 
下面的纹理是一种漫反射纹理的岩壁:  

<!--The following texture is a diffuse texture for a rock wall:
![漫反射纹理的岩壁](https://github.com/Moontabu/mypics/blob/main/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20210817151830.png)-->
