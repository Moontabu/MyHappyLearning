<!--⦁	Ambient Occlusion  -->  

⦁  环境光遮挡  

<!--Ambient occlusion is a grayscale texture that specifies how exposed each pixel is to ambient lighting. The darker the value the less light it receives. It is a quite simple technique and tends to give great results.-->  
环境遮挡是一种灰度纹理，它指定了每个像素在环境光照下的暴露程度。值越深，接收到的光越少。这是一种相当简单的技巧，往往会产生很好的效果。  


<!--The following texture is the ambient occlusion map for the rock wall example: -->   
下面的纹理是岩壁例子的环境遮挡贴图:


 
<!--F 2.5 Ambient occlusion sample -->   
F 2.5 环境闭塞的样本
   
![](https://github.com/Moontabu/mypics/blob/97e333b20fe19a64c95f7414fdf67bc0735067c9/0ffb40984570105e0f9215de11d8bff.png)  

<!--As we can see in the rock cracks the occlusion value is darker, so light will be less effective there.  -->  
正如我们在岩石裂缝中看到的，遮挡值更暗，所以光在那里的效果会更差。  


<!--⦁	Roughness/ Glossiness map -->  
⦁	粗糙度/光泽度地图  

<!--Roughness maps are grayscale images that specify the irregularities of each pixel, so determines the light deviation that certain pixel would have. The greater the value the rougher the surface will be. In the case of the rock the whole texture will be white, since rocks are rough. -->   
粗糙度图是指定每个像素的不规则性的灰度图像，因此决定了某些像素的光线偏差。数值越大，表面就越粗糙。在岩石的情况下，整个纹理将是白色的，因为岩石是粗糙的。


<!--⦁	Metallic map  -->  
⦁	金属地图  

<!--Metallic textures are grayscale images that specify the metalness of each pixel, the greater the value the more metallic it will be. In the example of the rock the texture would be filled with black, again the good practice in this case is to use a single value to specify the metalness, this way we avoid having too many textures in the GPU.  -->  
金属纹理是指定每个像素的金属性的灰度图像，值越大，它的金属性越强。在岩石的例子中，纹理将被黑色填充，在这种情况下的良好实践是使用一个单一的值来指定金属性，这样我们可以避免在GPU中有太多的纹理。


<!--⦁	Grayscale Images  -->  
⦁   灰度图像  

<!--A grayscale image is such image where the Red, Green,Blue and alpha channels hold the same number. So theoretically we do not need all the channels to hold that information, one single channel is able to carry all the information needed. We can take advantage of this situation by combining different grayscale images in a single one. For example, we can join the metallic map, the ambient occlusion map, the heightmap and the specular map in a-->  
  
α
一个灰度图像是这样的图像，其中红，绿，蓝和alpha(α：第一個希腊字母)通道持有相同的数字。所以从理论上讲，我们不需要所有的通道来承载这些信息，一个通道就可以承载所有需要的信息。我们可以利用这种情况，将不同的灰度图像合并到一个单一的图像中。例如，我们可以加入金属贴图，环境遮挡贴图， **【这句不完整，无法翻译】**

<!--single image giving to each channel the value of each one of the maps. This way we can have only one texture loaded instead of four.  -->  

单个图像给予每个通道的每个地图的值。这样我们就可以只加载一个纹理而不是四个。  

<!--Recently Unity released a new rendering pipeline and changed most of the materials that were used previously. Most of them uses this technique to optimize the usage of the GPU.-->  

最近Unity发布了一个新的渲染管道，并改变了之前使用的大部分材料。他们大多数使用这种技术来优化GPU的使用。
