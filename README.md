# Edge Detection in Java

Implementations of Image Segmentation

Segmentation partitions an image into distinct regions containing each pixels with similar attributes.
To be meaningful and useful for image analysis and interpretation, the regions should strongly
relate to depicted objects or features of interest. Meaningful segmentation is the first step from lowlevel image processing transforming a greyscale or colour image into one or more other images to
high-level image description in terms of features, objects, and scenes. The success of image analysis
depends on reliability of segmentation, but an accurate partitioning of an image is generally a very
challenging problem.

Segmentation techniques are either contextual or non-contextual. The latter take no account of
spatial relationships between features in an image and group pixels together on the basis of some
global attribute, e.g. grey level or colour. Contextual techniques additionally exploit these
relationships, e.g. group together pixels with similar grey levels and close spatial locations.

## EDGE DETECTION

Edge detection includes a variety of mathematical methods that aim at identifying points in a digital
image at which the image brightness changes sharply or, more formally, has discontinuities. The
points at which image brightness changes sharply are typically organized into a set of curved line
segments termed edges. Most of the shape information of an image is enclosed in edges. So first we
detect these edges in an image and by using these filters and then by enhancing those areas of image
which contains edges, sharpness of the image will increase and image will become clearer.

- Prewitt Operator
- Sobel Operator
- Robinson Compass Masks
- Krisch Compass Masks
- Laplacian Operator

## Split-and-merge segmentation

The top-down split-and-merge algorithm considers initially the entire image to be a single region
and then iteratively splits each region into subregions or merges adjacent regions until all regions
become uniform or until the desired number of regions have been established.

A common splitting strategy for a square image is to divide it recursively into smaller and smaller
quadrants until, for any region R, the uniformity predicate P(R) is TRUE. The strategy builds a topdown quadtree: if P(image) is FALSE, the image is divided into four quadrants; if P(quadrant) is
FALSE, the quadrant is divided into subquadrants; and so on:

![](/images/splitandmerge.jpg)

The splitting stage alternates with a merging stage, in which two adjacent regions Ri
 and Rj
 are
combined into a new, larger region if the uniformity predicate for the union of these two regions,
P(Ri
 R ∪ R j
), is TRUE.
## EDGE LINKING THROUGH HOUGH TRANSFORM

Hough transform can be used for pixel linking and curve detection. The straight line represented by
y=mx+c can be expressed in polar coordinate system as,

ρ = xcos(θ)+ ysin(θ) …………………..(i)

Where ρ,θ defines a vector from the origin to the nearest pointon the straight line y=mx+c. this
vector will be perpendicular from the origin to the nearest point to the line as shown in the below
figure. 

![](/images/straightline.jpg)

Any line in the x, y plane corresponds to the point in the 2D space defined by the parameter and θ.
This the Hough transform of a straight line in the x,y plane is a single point in the ρ, θ space and
these points should satisfy the given equation with x1,y1 as constants. Thus the locus of all such
lines in the x, y plane corresponds to the particular sinusoidal curve in the ρ, θ space.
