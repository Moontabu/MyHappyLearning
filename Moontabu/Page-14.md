<!--They can be also used to blend in a natural way between different materials. In the following image a heightmap has been used to determine which of both materials should be displayed, normally it is calculated in the shader. -->   
它们也可以用来在不同的材料之间以一种自然的方式混合。在下面的图片中，高度图被用来确定两种材质中应该显示哪一种，通常它是在着色器中计算的。

![](https://github.com/Moontabu/mypics/blob/535993eef6569b660e062b9dd5d0e41ff44a075a/871a0857933cbbbce0548eb94dfb3dc.png)
 
F 2.3 Height blending sample  

F 2.3 高度混合样品  

<!--The following heightmap is the one used for the previous rock wall example: -->    
下面的高度图是用于前面的岩壁例子:  

![](https://github.com/Moontabu/mypics/blob/535993eef6569b660e062b9dd5d0e41ff44a075a/8358757819520d93a0a74fe4a70d660.png)

 
F 2.4 Heightmap  样本


⦁	Specular Map  
⦁   镜面映射

<!--Specular maps are grayscale images that determine how shiny and reflective a surface is. The higher the value the brighter and reflective will be the pixel.-->  高光贴图是一种灰度图像，它决定了一个表面的亮度和反射程度。值越高，像素就越亮，并且会反射。  



<!--In the case of the rock that we have been seeing, the specular map would be just black, since rocks are not reflective. Normally a texture to specify that each pixel is black won’t be used, we would just specify that the specular value for the whole material is 0.-->   
在我们看到的岩石的情况下，高光贴图是黑色的，因为岩石是不反射的。通常情况下，指定每个像素为黑色的纹理不会被使用，我们只会指定整个材质的高光值为0。
