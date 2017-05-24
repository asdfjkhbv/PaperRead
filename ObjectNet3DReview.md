# Title: ObjectNet3D: A Large Scale Database for 3D Object Recognition
## keyword: Object3D datasets.
## Abstract INFO:
    Object3D : consists of 100 categories, 90127 images, 201888 objects and 44137 3D shapes.
## Introduction INFO
    Datasets Name:
	

| DatasetsName |# categories |   # images  |# 3D shapes |# 3D shape type |3D annotation type |
| --- | --- | --- | --- | --- | --- | 
| 3D Object [28]|10  |6,675     |  nan   | nan    | discretized view    |     
| EPFL  Car [23]  | 1    |2,299     |nan     |   nan  |  continuous view   |     
|  NYU Depth [29] | 894 |1,449     |nan     |nan     |depth     |     
|  SUN RGB-D [32]  | ~800     | 10,355    | nan    | nan    | depth    |    
|  KITTI [10]  | 2    | 14,999    |  nan   | 3D point clouds    |  3D point   |     
|  IKEA [20]   | 11    |   759  |   213  |  nan   | 2D-3D alignment    |     |
|  PASCAL3D+ [40]   |  12   |  30,899   |  79   |   3D CAD models  | 2D-3D alignment    |     
|   ObjectNet3D (this)  |   100  |   90,127  |   44,161  |   3D CAD models  |    2D-3D alignment |     
\

## 3D Shape retrieval (find the most similar 3D shapes to a given 2D object.
    Baseline method: GoogLeNet pretrained on ImageNet learn the embedding.
    What it the embedding?
    We learn a feature embedding for each category among the 45 categories where we have 3D shapes from ShapeNetCore.
    Explanation: a embedding feature from a category (45 core categories in ShapeNetCore). Is that mean the embedding feature contrain all the shape in 45 shapes?
    
    but the origin images has multi-objects in it. So it use mimic real images. it use randomly background images from SUN database and the render images(it from 100 view point 3D shape )
