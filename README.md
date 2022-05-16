# 3D Object Reconstruction Based on 2D Images
In this project, I reconstructed 3D objects from stereoscopic image pairs using triangulation and the eight-point algorithm. More specifically, I derived the depth of each point on the object by computing the essential matrix and fundamental matrix. These are then used to reconstruct the 3D point cloud that shows the object from different angles.

For this task, two slightly different images are given as input. They are taken from different angles.

<img src="https://github.com/HonglingLei/3D-Object-Reconstruction-Based-on-2D-Images/blob/main/data/im1.png" height="200" />
<img src="https://github.com/HonglingLei/3D-Object-Reconstruction-Based-on-2D-Images/blob/main/data/im2.png" height="200" />


## Proof about mirror reflection
Suppose that a camera views an object and its reflection in a plane mirror. It can be proven that this situation is equivalent to having two images of the object which are related by a skew-symmetric fundamental matrix. Proof is as below.

<img src="https://github.com/HonglingLei/3D-Object-Reconstruction-Based-on-2D-Images/blob/main/data/mirror_problem.png" height="600" />


## Formula Derivation: the Eight-Point Algorithm
Aw = 0, where A is a 4x4 matrix and w is a 4x1 vector of the 3D coordinates in the homogeneous form.

<img src="https://github.com/HonglingLei/3D-Object-Reconstruction-Based-on-2D-Images/blob/main/data/formula_proof.png" height="600" />


## Epipolar lines
Below is the visualization of the epipolar lines. I selected some points on the left image, and the corresponding epipolar lines are shown on the right image. 

<img src="https://github.com/HonglingLei/3D-Object-Reconstruction-Based-on-2D-Images/blob/main/data/displayEpipolarF_eg1.png" height="400" />


## 3D Reconostruction
After computing the fundamental matrix, essential matrix, and epipolar correspondence using RANSAC searching, I got the following reconstruction results.

<img src="https://github.com/HonglingLei/3D-Object-Reconstruction-Based-on-2D-Images/blob/main/data/Screen%20Shot%202022-03-28%20at%2011.59.26%20PM.png" height = "300"><img src="https://github.com/HonglingLei/3D-Object-Reconstruction-Based-on-2D-Images/blob/main/data/Screen%20Shot%202022-03-29%20at%2012.02.24%20AM.png" height = "300">

<img src="https://github.com/HonglingLei/3D-Object-Reconstruction-Based-on-2D-Images/blob/main/data/Screen%20Shot%202022-03-29%20at%2012.03.47%20AM.png" height = "300"><img src="https://github.com/HonglingLei/3D-Object-Reconstruction-Based-on-2D-Images/blob/main/data/Screen%20Shot%202022-03-29%20at%2012.07.38%20AM.png" height = "300">

<img src="https://github.com/HonglingLei/3D-Object-Reconstruction-Based-on-2D-Images/blob/main/data/Screen%20Shot%202022-03-29%20at%2012.14.56%20AM.png" height = "300">

We can clearly see the 3D shape of this temple. Even though we couldn't really observe the back of the temple in the given 2D images, the reconstructed 3D graphs help us see it from all angles.
