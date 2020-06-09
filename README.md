# Visualision of convex hull overlap from CellexalVR

This is the python code that processes and visualises the output from the [ConvexHullGenerator.cs](https://github.com/sonejilab/cellexalvr/blob/ConvexHullOverlap/Assets/Scripts/AnalysisLogic/ConvexHullGenerator.cs) in CellexalVR.


## Methods and ideas

In an attempt to prove that dimension reducing single cell RNA sequenced data seperates cell populations more three dimensens rather than two, I used an area based approach. The idea was to pairwise compare cell populations that are defined from the raw data and see how much they overlap in 3D and 2D. A convex hull method was chosen where the convex hull of a population was calculated and the overlap in terms of area was compared. In 2D the areas of the convex hulls could simply be compared, in 3D the convex hulls were projected down to two dimensions first along 2048 angles and the angle with the minimum overlap, in terms of area, was chosen for each pair of cell populations. This was to attempt to emulate what a user would do when they look at two cell populations in a 3D point cloud and would rotate the point cloud to find the "best" viewing angle.

## Running the code

Some example data we used is in the "data" folder.

To obtain your own data, clone [CellexalVR](https://github.com/sonejilab/cellexalvr), checkout the ConvexHullOverlap branch, then either modify the CalculateOverlapAll function (in [ConvexHullGenerator.cs](https://github.com/sonejilab/cellexalvr/blob/ConvexHullOverlap/Assets/Scripts/AnalysisLogic/ConvexHullGenerator.cs)) to run on your data, or run CalculateOverlap2D and CalculateOverlap3D (also in [ConvexHullGenerator.cs](https://github.com/sonejilab/cellexalvr/blob/ConvexHullOverlap/Assets/Scripts/AnalysisLogic/ConvexHullGenerator.cs)) manually for each 2D or 3D dimension reduction you have.
