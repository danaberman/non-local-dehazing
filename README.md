# Non-Local Image Dehazing

<img height="285px" width="200px" align="right" src="http://www.eng.tau.ac.il/~berman/images/cityscape_half.jpg">

This is the source code implementing the non-local single image dehazing algorithm described in the paper:

[Non-Local Image Dehazing. Berman, D. and Treibitz, T. and Avidan S., CVPR2016](https://www.eng.tau.ac.il/~berman/NonLocalDehazing/NonLocalDehazing_CVPR2016.pdf)



If you use this code, please cite our paper.

#### bibtex

>    @inproceedings{NonLocalImageDehazing,    
>      title={Non-Local Image Dehazing},    
>      author={Berman, D. and Treibitz, T. and Avidan, S.},    
>      booktitle={IEEE Conf. CVPR},    
>      year={2016},
>    }




## Getting Started

### System Requirements:
The code requires MATLAB, and was tested on windows.

### Demo
1. Change MATLAB's directory to the folder the code was extracted to.
2. Run the file demo_non_local_dehazing.m in order to see the algorithm's
perfomance on the attached images.

### Dehazing other images
This code requires a pre-computed air-light vector (RGB components) for each image. 
This value can be computed by various methods, e.g., the [Dark Channel Prior](https://www.mathworks.com/matlabcentral/fileexchange/46147-single-image-haze-removal-using-dark-channel-prior) (and soon our method, too).
The air-light value for the demo images is saved in the text file accompanying each image. 
This file also contains a gamma value for each image. These value were taken from the [result pages of the paper: "Dehazing using Color-Lines"](http://www.cs.huji.ac.il/~raananf/projects/dehaze_cl/results/).

The gamma value is required since the image formation model applies to the linear images, where each pixel's value is directly related to the number of photons received at that location on the sensor. 
A non-linear tone-mapping is applied in camera and most of the images we see are not linear. The gamma value approximates the inverse mapping of the pixels' values to linear.

Despite that, **for new images, I recommend trying gamma=1 first** (this is the default). It often works even though it is not physically accurate.


## Authors
Dana Berman, *danamena@post.tau.ac.il*


## License
 
The software code of the non-local image dehazing algorithm is provided for non-commercial use under the attached [LICENSE.md](LICENSE.md)
