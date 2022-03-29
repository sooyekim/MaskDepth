## Layered Depth Refinement with Mask Guidance
### CVPR 2022
[Soo Ye Kim](https://sites.google.com/view/sooyekim)<sup>1</sup>  
<sup>1</sup>KAIST

### Abstract
<div style="text-align: left">
Depth maps are used in a wide range of applications from 3D rendering to 2D image effects such as Bokeh. However, those predicted by single image depth estimation (SIDE) models often fail to capture isolated holes in objects and/or have inaccurate boundary regions. Meanwhile, high-quality masks are much easier to obtain, using commercial auto-masking tools or off-the-shelf methods of segmentation and matting or even by manual editing. Hence, in this paper, we formulate a novel problem of mask-guided depth map refinement that utilizes a generic mask to refine the depth prediction of SIDE models. Our framework performs layered refinement and inpainting/outpainting, decomposing the depth map into two separate layers signified by the mask and the inverse mask. As datasets with both depth and mask annotations are scarce, we propose a self-supervised learning scheme that uses arbitrary masks and RGB-D datasets. We empirically show that our method is robust to different types of masks and initial depth predictions, accurately refining depth values in inner and outer mask boundary regions. We further analyze our model with an ablation study and demonstrate results on real applications.
</div>

<html>
<!--     <head>
        <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
        
        <meta name="viewport" content="width=device-width, initial-scale=1" />

        <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>

        <link rel="stylesheet" type="text/css" href="https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/5.1.0/css/bootstrap.min.css" />

        <link rel="stylesheet" type="text/css" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css" />
    </head> -->
    <body>

<p>
    <div style="height:140px; margin:0px auto 0px auto; position:relative; width:780px;">
        <select class="form-control" style="height:140px; left:0px; position:absolute; top:0px; width:300px;" multiple="multiple"></select>
        <button class="btn btn-outline-primary" style="height:140px; left:310px; position:absolute; top:0px; width:150px;">Input<br>image</button>
        <button class="btn btn-outline-primary" style="height:40px; left:470px; position:absolute; top:0px; width:150px;">DPT</button>
        <button class="btn btn-outline-primary" style="height:40px; left:470px; position:absolute; top:50px; width:150px;">Ours</button>
        <button class="btn btn-outline-primary" style="height:40px; left:470px; position:absolute; top:100px; width:150px;">Boosting</button>
        <button class="btn btn-outline-primary" style="height:140px; left:630px; position:absolute; top:0px; width:150px;">Mask<br>(for ours)</button>
    </div>
</p>

<p>
    <img style="margin:0px auto 0px auto; max-height:800px; max-width:800px;"></img>
    <img style="margin:0px auto 0px auto; max-height:800px; max-width:800px;"></img>
    <img style="margin:0px auto 0px auto; max-height:800px; max-width:800px;"></img>
    <img style="margin:0px auto 0px auto; max-height:800px; max-width:800px;"></img>
    <img style="margin:0px auto 0px auto; max-height:800px; max-width:800px;"></img>
</p>

<div style="background-color:#FFFFFF; bottom:0px; font-size:14px; left:0px; padding:10px; position:fixed; right:0px; text-align:center;">
    All images are from <a href="https://unsplash.com/">unsplash</a>, <a href="https://pixabay.com/">pixabay</a> and <a href="https://stock.adobe.com/">Adobe Stock</a>.
    <br>
    <b>DPT</b>: Ranftl et al., Vision Transformers for Dense Prediction, ICCV, 2021.
    <br>
    <b>Boosting</b>: Miangoleh et al., Boosting Monocular Depth Estimation Models to High-Resolution via Content-Adaptive Multi-Resolution Merging, CVPR, 2021. 
</div>

<script type="text/javascript">
    jQuery(window.document).ready(function () {
        jQuery('select')
            .on('change', function() {
                jQuery('img').eq(0)
                    .attr({
                        'src': 'comparisons/rgb/' + jQuery(this).val() + '.jpg'
                    })
                ;

                jQuery('img').eq(1)
                    .attr({
                        'src': 'comparisons/dpt/' + jQuery(this).val() + '_depth.png'
                    })
                ;

                jQuery('img').eq(2)
                    .attr({
                        'src': 'comparisons/ours/' + jQuery(this).val() + '_pred.png'
                    })
                ;

                jQuery('img').eq(3)
                    .attr({
                        'src': 'comparisons/boosting/' + jQuery(this).val() + '.png'
                    })
                ;

                jQuery('img').eq(4)
                    .attr({
                        'src': 'comparisons/mask/' + jQuery(this).val() + '_mask.png'
                    })
                ;

                jQuery('img')
                    .each(function() {
                        (new Image()).src = jQuery(this).attr('src');
                    })
                ;
            })
            .each(function() {
                for (let strSample of [
                    'AdobeStock_63181133',
                ]) {
                    jQuery(this)
                        .append(jQuery('<option></option')
                            .attr({
                                'value': strSample
                            })
                            .text(strSample)
                        )
                }

                jQuery(this)
                    .val('AdobeStock_63181133')
                ;

                jQuery(this).triggerHandler('change');
            })
        ;

        jQuery('button')
            .on('mouseover', function() {
                jQuery('button')
                    .addClass('btn-outline-primary')
                    .removeClass('btn-primary')
                ;

                jQuery('button').eq(jQuery(this).index() - 1)
                    .addClass('btn-primary')
                    .removeClass('btn-outline-primary')
                ;

                jQuery('img')
                    .css({
                        'display': 'none'
                    })
                ;

                jQuery('img').eq(jQuery(this).index() - 1)
                    .css({
                        'display': 'block'
                    })
                ;
            })
            .eq(0)
                .each(function() {
                    jQuery(this).triggerHandler('mouseover');
                })
            .end()
        ;
    });
</script>

    </body>
</html>
