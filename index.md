## Layered Depth Refinement with Mask Guidance
#### CVPR 2022
[Soo Ye Kim](https://sites.google.com/view/sooyekim)<sup>1</sup>  
<sup>1</sup>KAIST

### Abstract
<div style="text-align: left">
Depth maps are used in a wide range of applications from 3D rendering to 2D image effects such as Bokeh. However, those predicted by single image depth estimation (SIDE) models often fail to capture isolated holes in objects and/or have inaccurate boundary regions. Meanwhile, high-quality masks are much easier to obtain, using commercial auto-masking tools or off-the-shelf methods of segmentation and matting or even by manual editing. Hence, in this paper, we formulate a novel problem of mask-guided depth map refinement that utilizes a generic mask to refine the depth prediction of SIDE models. Our framework performs layered refinement and inpainting/outpainting, decomposing the depth map into two separate layers signified by the mask and the inverse mask. As datasets with both depth and mask annotations are scarce, we propose a self-supervised learning scheme that uses arbitrary masks and RGB-D datasets. We empirically show that our method is robust to different types of masks and initial depth predictions, accurately refining depth values in inner and outer mask boundary regions. We further analyze our model with an ablation study and demonstrate results on real applications.
<br>
<br>
</div>

### Demo
<div style="text-align: left">
Select an image from the left and hover over the buttons on the right to compare the initial depth map by DPT [1] and the refined results by Boosting [2] and Ours. All images are from <a href="https://unsplash.com/">unsplash</a>, <a href="https://pixabay.com/">pixabay</a> and <a href="https://stock.adobe.com/">Adobe Stock</a>.  
<!-- <br>
<br>
[1] Ranftl et al., <a href="https://github.com/isl-org/DPT">Vision Transformers for Dense Prediction</a>, ICCV, 2021.
<br>
[2] Miangoleh et al., <a href="http://yaksoy.github.io/highresdepth/">Boosting Monocular Depth Estimation Models to High-Resolution via Content-Adaptive Multi-Resolution Merging</a>, CVPR, 2021. 
</div> -->
