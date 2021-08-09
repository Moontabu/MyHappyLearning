**一般目标**
<!--**General Objectives**-->  
主要目标是创建一个免费的Unity工具，允许用户创建PBR[1]贴图所需的所有纹理。
<!--The main objective is to create a free Unity tool that allow users to create all the textures needed for PBR [1] texturing procedurally.-->
目标
<!--Objectives:-->
开发一个Unity工具来生成程序纹理。
<!--⦁ Develop a Unity tool to generate procedural textures.-->  
开发一个易于使用和直观的GUI[2]。
<!--⦁ Develop an easy-to-use and intuitive GUI [2].-->  
提供不同的过滤器和声音，让用户尽可能多地控制纹理的外观。
<!--⦁ Provide different filters and noises to give users as much control as possible over the look of textures.-->  
在Unity的资产商店中发布它。
<!--⦁ Publish it in the Unity’s Asset Store.-->  
创建一个示例场景，只用这个工具创建的纹理。
<!--⦁ Create a sample scene that uses only textures created with this tool.-->
**特殊目标**
<!--⦁ **1.4 Specific Objectives**-->  
为了达到我的总体目标，我将以更具体的方式研究以下技术和目标:
<!--In order to achieve my general objectives, the following technologies and objectives will be studied in a more specific way:-->

⦁ GUI:  
Unity in-editor GUI:学习Unity的in-editor GUI是如何工作的，以便能够开发自定义工具，在本例中是基于节点的编辑器，但这些知识可以应用于任何工具，我想要在未来把这个开发出来。
<!--⦁ Unity in-editor GUI: Learn how Unity’s in-editor GUI works in order to be able to develop custom tools, in this case the node based editor, but this knowledge can be applied in any tool that I may want to develop in the future.-->  
基于节点的编辑器:理解并开发一个基于节点的编辑器界面，该界面允许创建可以在它们之间连接的不同节点，以便不同节点的连接将派生成特定的结果。以这样一种方式开发它，它不仅可以应用于程序纹理生成。
<!--⦁ Node based editor: Understand and develop a node based editor interface that allow the creation of different nodes that can be connected between them, so that the concatenation of different nodes will derive into a specific result. Develop it in such a way that it could be applied not only for procedural texture generation.-->  
纹理
<!--⦁ Texturing:-->  
声音:应用并理解一些用于程序纹理生成的声音算法。
<!--⦁ Noises: Apply and understand several noise algorithms used for procedural texture generation.-->  
过滤器:应用并理解图像过滤和处理技术，可以应用于程序纹理创建。
<!--⦁ Filters: Apply and understand image filtering and processing techniques that could be applied as well for procedural texture creation.-->  
PBR:了解如何每个纹理需要的PBR纹理工作，以便能够生成它们。
<!--⦁ PBR: Understand how each texture needed for PBR texturing works in order to be able to generate them.-->  
优化
<!--⦁ Optimizations:-->  
多线程:为了不冻结Unity编辑器，因为大多数节点将执行繁重的计算，该工具应该使用多线程。
<!--⦁ Multithreading: In order not to freeze the Unity editor, since most of the nodes will perform heavy computations, the tool should use multithreading.-->  
GPU[3]计算:如前所述，一些算法是繁重的计算，除了多线程，一些计算可以在GPU使用计算着色器完成。
<!--⦁ GPU[3] computations: As said before some algorithms are heavy to compute and in addition to multithreading some computations could be done in the GPU using compute shaders.-->  
使用
<!--⦁ Usage:-->  
使用这个工具为一个样本生成纹理。
<!--⦁ Use this tool to generate textures for a sample level.-->
