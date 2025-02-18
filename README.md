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
data can be imported/exported into the algorithm from exterior sources, including jupyter



open screen1.png. 
this is the logic for the object recognition algorithm, KNNobject.gh

you will see there are purple boxes. above the purple boxes are "logic #" texts. 

Logic 1 -  the directory of the file that we are going to identify  is in red. The file is BR-47472.3dm. Change this directory to whatever file you want to test. Ideally the file is a 3dm native, but doesn't need to be. From there the file is imported into 3d space. To create replicatable data, the geometry is repositioned to the origin and rebuilt using traingular meshes.  

Logic 2 - the rebuilt triangular mesh is sliced at n intervals across the x y and z planes. where the slices intersect, both internal and external,  a cartesian XYZ point is created.  The points are split into 3 buckets, and centroids are drawn between every 3 points. The newly created cartesian centroid XYZ point is used as search criteria to find the closest euclidean distance point from the slice intersection points. The two corresponding points are connected creating a vector with magnitude. This action is repeated for every centroid. 

Logic 3 - The length of each vector is calculated. Then the angle of each vector from an x,y, and z plane is calculated.

Logic 4 - This is the largest (and likely most confusing) aspect. Terms like ontologies, metaphysical, etc., are tossed around to add value by linking its functionality to its form, in digital parts. This algorithm steps outside of these and uses - what im coining - pataphysical symbologies. They are certain features that can be accelerated into higher dimensional space. The classification system I used for KNN are goemetrodynamic non-operational. This means higher dimensional classification. For example, in a airplane, it is no longer a "wing", it is now a blade. A wing is coded with 3 dimensional properties like lift and stiffness. A blade is a rudimentary placeholder that can reviece infinite coded properties - the naming is more inclusive, it can apply to a housefan. The classification system also ignores manufacturing features, as the goal is not to cater to manufacturing methods.
Each  blue/pink box is a classifier, and in the main object is recorded as a 0. Each vector length (Vlen) and each vector angle (VdegX, VdegY, VdegZ) is merged with the long string of 0's. 

Logic 5 - The first column of boxes are categories and create the headers for downstream ML use. 
The second row of boxes are imported csv files  where trained data exists (this is covered later) For now, important to know that  all of the classification categories have trained data in csv file exists and it is written into the file we are identifying.

Logic 6 - All the data is combined - the trained csv data - and the main file data - into a csv file. update the directory and click the button to export the csv. 

At this point in the process the workflow switches from rh/gh to jupyter. 
Launch any of the notebooks, for this example I am using extractorbar. They are all mostly the same with minor changes to accomodate the classifiation by dropping columns. 

![image](https://github.com/user-attachments/assets/de48306f-100f-4699-9dad-9025cd69b474)


With the main file csv exported correctly (and assuming the file auto uploads to the juyter directory, if not... upload) 
You will see in the "bar" extractor all columns are kept, except bar. The last two cells contain the export data - update the  directory. Run the cells. 
Run all of the jupyter notebooks.

back to rh/gh

Logic 7 - The left column of boxes contains the machine learning text files exported from jupyter for each object classification. These are  trained points as they relate to this object. 

Logic 8 - WIP (not that this isn't all wip) but it is the start of logistic regression.

