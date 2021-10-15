**注释：之前的页码均为PDF文件页码-1，此次开始更正为与PDF一样的页码。**    

<!--⦁	Procedural Texture Generation-->  
⦁	过程纹理生成

<!--As we have seen procedural content is such content generated through an algorithm, so procedural textures are defined by an algorithm. I like to think of it as a mathematical formula that determines the final output of the texture’s pixel. For example we can use the pixel position to determine its grayscale value, so that the greater the X position of the pixel the darker the value will be:  -->
正如我们所见，程序内容是通过算法生成的内容，所以程序纹理是由算法定义的。我喜欢把它看作一个决定纹理像素最终输出的数学公式。例如，我们可以用像素的位置来确定它的灰色透明度，这样像素的X位置越大，值就越深:

f(x,y) = x



<!--This simple formula applied to every pixel of a texture will give darker values to pixels in the left side of the texture. We could do the same but with its Y position, so upper pixels will look darker. --> 
这个简单的公式适用于纹理的每个像素，会给纹理左侧的像素带来较暗的值。我们也可以做同样的事情，但是用它的Y位置，所以上面的像素看起来会更暗。


f(x,y) = y

<!--As we can see it does not matter the resolution of the image we want to generate since its values will depend on this formula. Of course algorithms used are way more complex. --> 

正如我们所看到的，它与我们想要生成的图像的分辨率无关，因为它的值取决于这个公式。当然，使用的算法要复杂得多。  

<!--We can combine different formulas to get a more complex result.  
我们可以把不同的公式组合起来得到更复杂的结果。-->


<!--⦁	Noise Generation --> 

⦁	噪音的产生

<!--To achieve organic results there are different pseudo-random algorithms able to generate natural looking patterns, as well as variants of the same noise. This is a list of the most common noises used in procedural textures:-->  
为了获得有机的结果，有不同的伪随机算法能够生成自然的外观模式，以及相同噪声的变体。这是程序纹理中最常见的噪音列表:

<!-- Perlin Noise: --> 
 噪声:
 
<!--It was developed by Ken Perlin in 1983 in an attempt to give computer graphics a natural looking feel. It is a gradient noise that involve three main steps:-->    
它是由肯·佩林(Ken Perlin)在1983年开发的，目的是让计算机图形看起来更自然。它是一个梯度噪声，包括三个主要步骤:

<!--⦁	Defines a grid with randomly generated gradient vectors.-->    
⦁	用随机生成的梯度向量定义一个网格。


<!--⦁	Calculates	the	dot	product	between	the distance-gradient vectors.-->   
⦁	计算距离梯度向量之间的点积。


<!--⦁	Interpolates between those values.-->  
⦁	在这些值之间插入。
![](https://github.com/Moontabu/mypics/blob/f817846119a75a17cd919dca4d593e981205dd0d/9c450606234a1404f117a59baa0d41f.png)
