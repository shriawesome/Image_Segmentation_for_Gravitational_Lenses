# Image Segmentation for Gravitational Lenses
## 1. Gravitational Lenses
<p><img src="images/galaxy_lens2.png" align="center" width="20%" height="10%">
    <img src="images/galaxy_lens3.png" align="center" width="19%" height="10%">
    <img src="images/galaxy_lens.png" align="center" width="27%" height="15%"></p>

* Gravitational lenses are an observational phenomenon caused by the alignment of two galaxies separated by cosmological distances.
* The light from the background galaxy bends because of the gravitational forces from the foreground galaxy. 
* This causes the light from the background galaxy to appear to us on earth like a halo or `Einstein Ring`.

## 2. Image Segmentation
<p><img src="images/img_seg.png" align="center" width="30%" height="15%"></p>

* Image segmentation partitions an image into multiple segments on the pixel level.
* Objective is to draw a careful outline around the object that is detected so that you know exactly which pixels belong to the object and which does not.

## 3. Hardware Used
* We used Perlmutter at NERSC i.e National Energy Research Scientific Computing Center ranked as world's `5th most fastest computing platform`.
* It is a high-performance computing user facility operated by Lawrence Berkeley National Laboratory for the United States Department of Energy Office of Science.

<p><img src="images/nersc.png" width="20%" height="15%"></p>

## 4. Technology Stack
    | Functionality  | Tools |
    | ------------- | ------------- |
    | Programming Language  | Python3  |
    | Modules | Tensorflow, PyTorch, PIL, Keras, Scikit-learn, NumPy, matplotlib |

## 5. Dataset
* Worked accross 2 datasets namely CHAOS Dataset i.e. `Combined Healthy Abdominal Organ Dataset` and `Galaxy Lenses Simulation Dataset`

    | Dataset | Description|
    | ------------- | ----------- |
    | CHAOS Dataset | Train(~3000 images), Val(~600 images)  |
    | Galaxy Lenses Dataset | Train(~16,000 images), Val/Test(2000 images) |

    <figure><img src="images/chaos.png" align="center" width="30%" height="15%" title="CHAOS Dataset"><figcaption>CHAOS Dataset</figcaption>
    <img src="images/galaxy_simul.png" align="center" width="30%" height="15%"><figcaption>Galaxy Lenses Dataset</figcaption></figure>

## 6. Data Preprocessing
* Generated masks for the lenses(foreground galaxy) and the arcs(background galaxy) by:
    * Filtering pixel values >99% to extract lenses.
    * Filtering pixel values >95% for arcs.
* Performed pixel value normalization.
* Enhanced arcs brightness by scaling it to a factor of 10.

## 7. Algorithms
### 7.1. MSRF-Net Model
* MSRF-Net stands for `Multi-Scale Residual Fusion Network`.
* Designed for biomedical image segmentation 
* Able to exchange multi-scale features using a Dual-Scale Dense Fusion (DSDF) blocks. 
* Multi-scale fusion, that allows:
    1. Preservation of resolution
    2. Improved information flow
    3. Propagation of both high and low level features to obtain accurate segmentation maps.

  <img src="images/msrf.png" width="20%" height="10%"/>

### 7.2. IS-Net Model
* Inspired by the famous U-Net that made breakthrough in Segmentation in 2015.
* A U2-Net architecture, i.e., A U-Net made out of U-Net. 
* Has multiple RSU Blocks of different scales to capture contextual information. 
* Used Intermediate Supervision in the loss function to avoid over-fitting.
 
    <img src="images/isnet.png" width="20%" height="10%"/>

## Performance Evaluation
 <img src="images/table1.png" width="50%" height="50%"/>

## 8. Results
* Achieved a Mean IOU of 98%

 <img src="images/res_lens.png" width="50%" height="50%"/>

* Achieved a Mean IOU of 96%

 <img src="images/res_arcs.png" width="50%" height="50%"/>

 ## 9. Citation
 * @article{srivastava2021msrf,
 title={MSRF-Net: A Multi-Scale Residual Fusion Network for Biomedical Image Segmentation},
  author={Srivastava, Abhishek and Jha, Debesh and Chanda, Sukalpa and Pal, Umapada and Johansen, H{\aa}vard D and Johansen, Dag and Riegler, Michael A and Ali, Sharib and Halvorsen, P{\aa}l},
  journal={arXiv preprint arXiv:2105.07451},
  year={2021}
}

## 10. Contribution
* [Shrikant Kendre](https://github.com/shriawesome/)
* [Shobhit Srivastava](https://github.com/srivastavashobhit)
* [Brian Sisney](https://github.com/briansisney)
