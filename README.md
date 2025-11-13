# 3dv paper

This repository serves as my personal notebook, collecting papers of interest that I encounter anytime, anywhere.

## Table of Contents

- [Surface Reconstruction](#Surface-Reconstruction)
- [Extended](#Extended)


## Surface Reconstruction
>★★★★★☆☆☆☆☆

- __SuGaR: Surface-Aligned Gaussian Splatting for Efficient 3D Mesh Reconstruction and High-Quality Mesh Rendering.__ _Antoine Guédon, Vincent Lepetit._ __CVPR, 2024.__ [[`Paper`](https://arxiv.org/pdf/2311.12775)] [[`Code`](https://github.com/Anttwo/SuGaR)] ([`Note`]()) (★★★☆☆)

  <details>
  <summary> Notes </summary>  
    
  - For __constructing the SDF function__, all overlapping Gaussians on each pixel are considered, and the one with the __highest contribution__ (or whose center is closest to the pixel) is selected.  
    > __Question:__ _Does the regularization process select the Gaussian with the highest contribution to reduce its distance from the pixel, or the one closest to the pixel to enhance its contribution?_  
  - For aligning Gaussians with the surface, the 3D Gaussians are flattened into 2D Gaussians to better approximate the scene surface by __3-scales eigenvalue decomposition__.  
    > <img width="50%" height="50%" alt="image" src="https://github.com/user-attachments/assets/f8db32aa-11e4-4e7b-a4b6-c73edc051c1b" />
    
  </details>

- __2D Gaussian Splatting for Geometrically Accurate Radiance Fields.__ _Binbin Huang et.al._  __SIGGRAPH, 2024.__ [[`Paper`](https://arxiv.org/pdf/2403.17888)] [[`Code`](https://github.com/hbb1/2d-gaussian-splatting)] [[`Note`]()] (★★★★☆)

  <details>
  <summary>Notes</summary> 
    
  - For __multi-view consistency__, the 3D Gaussian volumes are flattened into 2D Gaussian disks by __construct 2d gaussian directly__. 
    ```
    const glm::vec2* scales
    ```
  - For mitigating the loss introduced by __the affine approximation of perspective projection__, __the homogeneous transformation__ is employed to project local Gaussian coordinates into pixel coordinates. 
    ``` 
    // Approximation:
    glm::mat3 cov3d = glm::transpose(S * R) * (S * R);
    glm::mat3 cov2d = glm::transpose(W * J) * glm::transpose(cov3d) * (W * J);
    // Homogeneous:
    T = glm::transpose(splat2world) * world2ndc * ndc2pix; 
    ```
  - For reducing instability caused by determinant explosions during __the inverse transformation of pixel points into the uv-space for 2D Gaussian computation__, the method __replaces point-based transformations with plane-based transformations__.
    > A point $p$ is transformed by $p'=M\cdot p$ , while a plane $h$ is transformed by $h'=M^{-T}\cdot h$
    
  <details>

- __High-quality Surface Reconstruction using Gaussian Surfels.__ _Pinxuan Dai, Jiamin Xu et.al._ __SIGGRAPH, 2024.__ [[`Paper`](https://arxiv.org/pdf/2404.17774)] [[`Code`](https://github.com/turandai/gaussian_surfels)] [[`Note`]()] (Unread)

- __GSDF: 3DGS Meets SDF for Improved Neural Rendering and Reconstruction.__ _Mulin Yu et.al._  __NeurIPS, 2024.__ [[`Paper`](https://arxiv.org/pdf/2403.16964)] [[`Code`](https://github.com/city-super/GSDF)] [[`Note`]()] (Unread)

- __GS2Mesh: Surface Reconstruction from Gaussian Splatting via Novel Stereo Views.__ _Yaniv Wolf et.al._ __ECCV, 2024.__ [[`Paper`](https://arxiv.org/pdf/2404.01810)] [[`Code`](https://github.com/yanivw12/gs2mesh/tree/main)] [[`Note`]()] (Unread)

- __Gaussian Opacity Fields: Efficient Adaptive Surface Reconstruction in Unbounded Scenes.__ _Zehao Yu et.al._ __TOG, 2024.__ [[`Paper`](https://arxiv.org/pdf/2404.10772)] [[`Code`](https://github.com/autonomousvision/gaussian-opacity-fields)] [[`Note`]()] (★★★☆☆)

- __RaDe-GS: Rasterizing Depth in Gaussian Splatting.__ _Baowen Zhang et.al._ __ArXiv, 2024.__ [[`Paper`](https://arxiv.org/pdf/2406.01467)] [[`Code`](https://github.com/HKUST-SAIL/RaDe-GS)] [[`Note`]()] (Unread)

- __3DGSR: Implicit Surface Reconstruction with 3D Gaussian Splatting.__ _XIAOYANG LYU et.al._ __TOG, 2024__ [[`Paper`](https://arxiv.org/pdf/2404.00409)] [`No Code`] [[`Note`]()] (Unread)

- __Surface Reconstruction from 3D Gaussian Splatting via Local Structural Hints.__ _Qianyi Wu et.al._ __ECCV, 2024__ [[`Paper`](https://wuqianyi.top/media/GSRec.pdf)] [[`Code`](https://github.com/QianyiWu/gsrec)] [[`Note`]()] (Unread)

- __PGSR: Planar-based Gaussian Splatting for Efficient and High-Fidelity Surface Reconstruction.__ _Danpeng Chen et.al._ __TVCG, 2024__ [[`Paper`](https://arxiv.org/pdf/2406.06521)] [[`Code`](https://github.com/zju3dv/PGSR)] [[`Note`]()] (★★★☆☆)

- __Trim 3D Gaussian Splatting for Accurate Geometry Representation.__ _Lue Fan, Yuxue Yang et.al._ __ArXiv, 2024.__ [[`Paper`](https://arxiv.org/pdf/2406.07499)] [[`Code`](https://github.com/YuxueYang1204/TrimGS)] [[`Note`]()] (Unread)

- __MonoGSDF: Exploring Monocular Geometric Cues for Gaussian Splatting-Guided Implicit Surface Reconstruction.__ _Kunyi Li et.al._ __ArXiv, 2024.__ [[`Paper`](https://arxiv.org/pdf/2411.16898)] [`No Code`] [[`Note`]()] (Unread)

- __SolidGS: Consolidating Gaussian Surfel Splatting for Sparse-View Surface Reconstruction.__ _Mulin Yu et.al._  __NeurIPS, 2024.__ [[`Paper`](https://arxiv.org/pdf/2412.15400)] [`No Code`] [[`Note`]()] (Unread)

- __GausSurf: Geometry-Guided 3D Gaussian Splatting for Surface Reconstruction.__ _Jiepeng Wang et.al._ __ArXiv, 2024.__ [[`Paper`](https://arxiv.org/pdf/2411.19454)] [[`Code`](https://github.com/jiepengwang/GausSurf)] ([`Note`]()) (Unread)

- __αSurf: Implicit Surface Reconstruction for Semi-Transparent and Thin Objects with Decoupled Geometry and Opacity .__ _Keyang Ye et.al._ __3DV, 2025.__ [[`Paper`](https://arxiv.org/pdf/2303.10083)] [[`Code`](https://github.com/ChikaYan/alphasurf)] [[`Note`]()] (Unread)

- __Sparse2DGS: Geometry-Prioritized Gaussian Splatting for Surface Reconstruction from Sparse Views.__ _Jiang Wu et.al._ __CVPR, 2025.__ [[`Paper`](https://arxiv.org/pdf/2504.20378)] [[`Code`](https://github.com/Wuuu3511/Sparse2DGS)] [[`Note`]()] (Unread)

- __Volumetric Surfaces: Representing Fuzzy Geometries with Layered Meshes.__ _Stefano Esposito et.al._ __CVPR, 2025.__ [[`Paper`](https://arxiv.org/pdf/2409.02482)] [[`Code`](https://github.com/autonomousvision/volsurfs/tree/main)] [[`Note`]()] (Unread)

- __FatesGS: Fast and Accurate Sparse-View Surface Reconstruction Using Gaussian Splatting with Depth-Feature Consistency.__ _Han Huang, Yulun Wu et.al._ __AAAI, 2025 Oral.__ [[`Paper`](https://arxiv.org/pdf/2501.04628)] [[`Code`](https://github.com/yulunwu0108/FatesGS)] [[`Note`]()] (Unread)

- __Sparis: Neural Implicit Surface Reconstruction of Indoor Scenes from Sparse Views.__ _Yulun Wu, Han Huang et.al._ __AAAI, 2025 Oral.__ [[`Paper`](https://arxiv.org/pdf/2501.01196)] [[`Code`](https://github.com/yulunwu0108/Sparis/tree/master)] [[`Note`]()] (Unread)

- __When Gaussian Meets Surfel: Ultra-fast High-fidelity Radiance Field Rendering.__ _Keyang Ye et.al._ __TOG, 2025.__ [[`Paper`](https://arxiv.org/pdf/2504.17545)] [`No Code`] [[`Note`]()] (Unread)

- __Quadratic Gaussian Splatting: High Quality Surface Reconstruction with Second-order Geometric Primitives.__ _Ziyu Zhang, Binbin Huang et.al._  __ICCV, 2025.__ [[`Paper`](https://arxiv.org/pdf/2411.16392)] [[`Code`](https://github.com/will-zzy/QGS)] [[`Note`]()] (★★★★☆)

- __MGSR: 2D/3D Mutual-boosted Gaussian Splatting for High-fidelity Surface Reconstruction under Various Light Conditions.__ _Qingyuan Zhou et.al._ __ICCV, 2025.__ [[`Paper`](https://arxiv.org/pdf/2503.05182)] [[`Code`](https://github.com/TsingyuanChou/MGSR)] [[`Note`]()] (Unread)

- __SurfaceSplat: Connecting Surface Reconstruction and Gaussian Splatting.__ _Zihui Gao, Jia-Wang Bian et.al._ __ICCV, 2025.__ [[`Paper`](https://arxiv.org/pdf/2507.15602)] [[`Code`](https://github.com/aim-uofa/SurfaceSplat)] [[`Note`]()] (Unread)

- __PolGS: Polarimetric Gaussian Splatting for Fast Reflective Surface Reconstruction.__ _Yufei Han et.al._ __ICCV, 2025.__ [[`Paper`](https://arxiv.org/pdf/2509.19726)] [[`Code`](https://github.com/PRIS-CV/PolGS)] [[`Note`]()] (Unread)

- __MILo: Mesh-In-the-Loop Gaussian Splatting for Detailed and Efficient Surface Reconstruction.__ _Antoine Guédon, Diego Gomez et.al._ __TOG, 2025.__ [[`Paper`](https://arxiv.org/pdf/2506.24096)] [[`Code`](https://github.com/Anttwo/MILo)] [[`Note`]()] (Unread)

- __Multi-view Normal and Distance Guidance Gaussian Splatting for Surface Reconstruction.__ _Bo Jia et.al._ __ArXiv, 2025.__ [[`Paper`](https://arxiv.org/pdf/2508.07701)] [[`Code`](https://github.com/Bistu3DV/MND-GS)] [[`Note`]()] (Unread)

- __Accurate and Complete Surface Reconstruction from 3D Gaussians via Direct SDF Learning.__ _Wenzhi Guo et.al._ __ArXiv, 2025.__ [[`Paper`](https://arxiv.org/pdf/2509.07493)] [[`Code`](https://github.com/DARYL-GWZ/DIGS)] [[`Note`]()] (Unread)

- __GS-2M: Gaussian Splatting for Joint Mesh Reconstruction and Material Decomposition.__ _D. M. Nguyen et.al._ __ArXiv, 2025.__ [[`Paper`](https://arxiv.org/pdf/2509.22276)] [[`Code`](https://github.com/ndming/GS-2M/tree/main)] [[`Note`]()] (Unread)


- __GVKF: Gaussian Voxel Kernel Functions for Highly Efficient Surface Reconstruction in Open Scenes.__ _Gaochao Song, Chong Cheng et.al._ __NeurIPS, 2025.__ [[`Paper`](https://arxiv.org/pdf/2411.01853)] [[`Code`](https://github.com/3DAgentWorld/GVKF/tree/main)] [[`Note`]()]


## Extended
  
- Computational Geometry: Algorithms and Applications. book 
- Geometric Tools for Computer Graphics. book
- GeoSplat: A Deep Dive into Geometry-Constrained Gaussian Splatting. paper
- Triangle Splatting for Real-Time Radiance Field Rendering
