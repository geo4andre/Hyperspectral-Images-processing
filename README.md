# Hyperspectral-Images-processing

Project for Machine Learning course at MSc in Data Science 

## Hyperspectral images (HSIs): 
An HSI depicts a specific scene at several (L) narrow
continuous spectral bands (actually, they visualize the reflectance of the depicted scene
in various spectral bands). It can be represented by a MxNxL three-dimensional cube,
where the first two dimensions correspond to the spatial information, while the third
corresponds to the spectral information. Thus, the (i,j) pixel in such an image, i=1,…,M,
j=1,…,N, is represented by an L-dimensional vector (constituted by the corresponding
spectral bands), called the spectral signature of the pixel.

In several remote sensing applications, the HSIs (taken from satellites) that depict
specific scenes of the earth surface at a specific spatial resolution (that is, a single pixel
may represent an area from 3x3 m2, to, e.g., 100x100m2 or more). That is, each pixel is
likely to depict more than one materials depicted in the corresponding area of the
scene. Such pixels are called mixed pixels and they are the vast majority of the pixels in
the image. On the other hand, there are (usually) a few pixels that depict a single
material. These are called pure pixels.

## Processing in HSIs: 
The usual processing procedures in HSIs follow two main directions,
namely, the spectral unmixing and the classification (supervised, unsupervised).

## (a) Spectral unmixing (SU): 
The problem here is stated as follows: Assume that a set of
m spectral signatures corresponding to the pure pixels in the HSI under study (7 endmembers in our case which we extract from the picture) is
given. For a given pixel in the image, the aim is to determine the percentage
(abundance) to which each pure material contributes in its formation. It is clear,
that SU provides sub-pixel information for a given pixel. Speaking in mathematical
terms, let
(i) y be the (column L-dimensional) spectral signature of the pixel under study,
(ii) x1,… xm, be the spectral signatures (column L-dimensional vectors) of the pure
pixels in the image (each one corresponding to a pure material met in the
image) and
(iii) θ, the m-dimensional abundance vector of the pixel (its q-th coordinate
corresponds to the percentage to which the q-th pure pixel contributes to the
formation of the pixel under study).
Adopting the linear spectral unmixing hypothesis, the above quantities are related
as follows
y = X θ + η,
where η is an L-dimensional i.i.d., zero mean Gaussian noise vector. Note that, physically, the entries of θ should be nonnegative and (ideally) they should sum to one.


## (b) (Supervised) classification: 
In this case, the problem is stated as follows: Assume that all the pixels in the HSI under study are known to belong to one out of m known classes (7 endmembers in our case). Given a specific pixel, the aim is to determine the most suitable class to assign it.

In this project we refer to the so called “Salinas” HSI, which depicts an area of the Salinas valley in California, USA. It is a 220x120 spatial resolution HSI and consists of 204 spectral bands (from 0.2μm – 2.4μm) and its spatial resolution is 3.7m (that is, the HSI is a 220x120x204 cube). The data that will be used are in the files “Salinas_cube.mat” (the Salinas hypercube) and “Salinas_gt.mat” (the class label for each pixel).

In this project we have performed least squares with various different combinations of constraints for the first part and some classifiers for the second part.
