<!--⦁	Normal maps-->  
⦁   法线贴图

<!--Normal maps are used to simulate lighting of bumps over a surface of a low-poly model giving it the appearance of a high-poly model. Normally they are baked from a high-poly into a low-poly transfering the detail of the first into the other. -->  
法线贴图被用来模拟低多边形模型表面凹凸的照明，使其具有高多边形模型的外观。通常情况下，它们是从高聚到低聚，将第一个的细节转移到另一个。

<!--Normal maps use the RGB [4] channels of the image to give information about the X, Y and Z spatial coordinates. So for calculating lighting, instead of using a normal per-vertex, with normal maps we can use a normal per-pixel, this way we can increase detail by a lot. -->  

法线贴图使用图像的RGB[4]通道来提供关于X, Y和Z空间坐标的信息。因此，在计算光照时，我们可以使用法线贴图，而不是普通的逐顶点，这样我们就可以大大增加细节。  

<!--The following texture holds the normal information of each pixel from the previous rock wall. -->  
下面的纹理保存了之前岩壁上每个像素的正常信息。


   
![](8530de8293cce712526a42dc72e777b.png)
<!--F 2.2 Normal map sample -->  
2.2法线贴图的样本






<!--⦁	Height map -->  
高度图  

<!--Height maps hold information of each vertex height. Their grayscale value is used to determine the height. From a 0 (black) to 1 (white) value it is specified how high the vertex should be. The greater the number of vertices of the model the better will look the result, reason why, most of the time, they are used over tessellated surfaces, so they can provoke performance issues. -->  
高度图包含每个顶点高度的信息。它们的灰度值被用来确定高度。从0(黑色)到1(白色)是指定顶点应该有多高。模型的顶点数量越多，结果看起来就越好，这就是为什么，大多数时候，顶点是在镶嵌表面上使用的，所以它们可能会引发性能问题。

<!--They are most commonly used to make terrains, this way the terrain creation process is pretty much automatic once you have your height map defined. -->  
它们最常用于制作地形，这样一旦你定义了高度图，地形创建过程就会非常智能。
