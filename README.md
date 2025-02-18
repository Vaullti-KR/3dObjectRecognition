# 3dObjectRecognition
identify a 3d object

this is an algorithm that operates in 3d space. It is nontraditional. I, the author, do not have a background in computer science. My background is architecture and computational design. As such, if you have comments on specifics, I most likely cannot help. 

![image](https://github.com/user-attachments/assets/fcebe9b3-ec2c-4a02-bccc-35934900d552)

There are a few "dependencies" 

The first is rhino. Rhino is a graphing calcuator. Its free. 
https://www.rhino3d.com/download/rhino/evaluation/

Second is grasshopper. 
https://en.wikipedia.org/wiki/Grasshopper_3D

Third, jupyter.
https://jupyter.org/

What most (all) people don't realize: 
rhino/grasshopper runs headless
the algorithms can be automated
data can be imported into the algorithm from exterior sources, including jupyter



open screen1.png. 
this is the logic for the object recognition algorithm, KNNobject.gh

you will see there are purple boxes. above the purple boxes are "logic #" texts. 

Logic 1 -  the directory of the file that we are going to identify  is in red. The file is BR-47472.3dm. Change this directory to whatever file you want to test. Ideally the file is a 3dm native, but doesn't need to be. From there the file is imported into 3d space. To create replicatable data, the geometry is repositioned to the origin and rebuilt using traingular meshes.  

Logic 2 - the rebuilt triangular mesh is sliced at n intervals across the x y and z planes. where the slices intersect, both internal and external,  a cartesian XYZ point is created.  The points are split into 3 buckets, and centroids are drawn between every 3 points. The newly created cartesian centroid XYZ point is used as search criteria to find the closest euclidean distance point from the slice intersection points. The two corresponding points are connected creating a vector with magnitude. This action is repeated for every centroid. 
