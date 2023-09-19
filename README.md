# Optimizing Foliage Density Estimation for NYC

This project focuses on utilizing LiDAR data, acquired through aerial scans over New York City, to construct a detailed 3D representation of trees. A key aspect involves evaluating LiDAR's efficacy in calculating Leaf Area Index (LAI), a crucial metric for foliage density, giving us insights into ecosystem health. Comparative analysis demonstrated that LiDAR proves as effective as traditional methods, such as field measurements and point quadrant analysis, in accurately determining LAI. In this study, I focused on optimizing the computation speed for calculating intersections between Lidar points and their corresponding tree canopies. Specifically, Python compile time was improved from an exponential progression to a much more efficient linear one, reducing the time complexity from O(n^2) to O(n). This improvement was achieved by implementing three different approaches, utilizing GeoPandas, Dask for parallel and distributed processing, and recursion within Jupyter Lab.


## Note About Project Ownership and Contribution
This project is owned by the Environmental Fluid Mechanical Lab at Columbia University, and I am actively contributing to it. Please be advised that this project is an ongoing, confidential research endeavor expected to be finalized and potentially published within the coming year. Due to its nature, the project and associated paper contain confidential information, and it's currently not feasible to disclose the entire project or paper. However, **I am able to share the code I have worked on as a contributor**. Rest assured, updates regarding this project will be shared within this GitHub repository once the research reaches its completion.


## References
• [Optimizing Foliage Density Estimation for NYC](https://link.springer.com/article/10.1007/s00468-006-0119-6)


## Project Breakdown

### 1. Tree Representation Class
- A Python class, `Tree`, is defined to organize overlapping LiDAR points and their corresponding tree crowns. It holds the tree identifier and the associated LiDAR points.

### 2. Data Import
- LiDAR metrics and tree crown data are imported for analysis. Voxel metrics data and tree crown shapefiles are loaded to facilitate the subsequent processing.

### 3. LiDAR Points Clipping
- LiDAR points falling within the collective tree top area are clipped. This step ensures that subsequent analysis is focused on relevant data for each tree.

### 4. Traditional Clipping Approach
- This part of the code iterates through the trees, clipping LiDAR points for each tree based on its geometry. Leaf Area Index (LAI) calculations are performed, providing insights into foliage density.

### 5. Recursive Clipping Strategy
- A recursive approach is implemented to compute clipped geometries for each tree. This method effectively filters and clips LiDAR points for each tree geometry.

### 6. Dask Parallel Clipping Implementation
- A parallel clipping process is implemented using Dask for efficient computation. It significantly enhances the speed of clipping LiDAR points against tree geometries.

### 7. Random Tree Visualization
- A visualization component is included, allowing the random selection and plotting of a tree from the clipped trees.



<img width="890" alt="Screenshot 2023-09-18 at 8 21 39 pm" src="https://github.com/jyblackshaw/Optimizing-Foliage-Density-Estimation-for-NYC-/assets/68715353/827d2bf1-13a2-4f5c-95b1-fc736e3c730a">

<img width="890" alt="Screenshot 2023-09-18 at 8 20 02 pm" src="https://github.com/jyblackshaw/Optimizing-Foliage-Density-Estimation-for-NYC-/assets/68715353/1f859ee3-ccd5-4085-add6-2438b7bfca26">

<img width="890" alt="Screenshot 2023-09-18 at 8 20 48 pm" src="https://github.com/jyblackshaw/Optimizing-Foliage-Density-Estimation-for-NYC-/assets/68715353/c9e3a65b-462f-40e9-9c34-069ce4c50476">
