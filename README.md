# Boundary Tracing & Hough Transform

## Boundary Tracing

The boundery tracing algorithm is used to extract the contours of the objects (regions) 
from an image. When applying this algorithm it is assumed that the image with regions is 
either binary or those regions have been previously labeled. 

### Algorithm’s steps: 

- Search the image from top left until a pixel of a new region is found; this pixel P0
is the starting pixel of the region border. Define a variable dir which stores the 
direction of the previous move along the border from the previous border element 
to the current border element. Assign 
(a) dir = 0 if the border is detected in 4-connectivity (Fig. 6.1a) 
(b) dir = 7 if the border is detected in 8-connectivity (Fig. 6.1b) 

- Search the 3x3 neighborhood of the current pixel in an anti-clockwise direction, 
beginning the neighborhood search at the pixel positioned in the direction 
(a) (dir + 3) mod 4 (Fig. 6.1c) 
(b) (dir + 7) mod 8 if dir is even (Fig. 6.1d) 
(dir + 6) mod 8 if dir is odd (Fig. 6.1e) 
The first pixel found with the same value as the current pixel is a new boundary 
element Pn. Update the dir value. 

- If the current boundary element Pn is equal to the second border element P1 and if 
the previous border element Pn-1 is equal to P0, stop. Otherwise repeat step (2). 

- The detected border is represented by pixels P0 … Pn-2. 

## Circle Hough Transform brief explaination

The circle Hough Transform (CHT) is a basic feature extraction 
technique used in digital image processing for detecting circles in imperfect images.
The circle candidates are produced by “voting” in the Hough 
parameter space and then selecting local maxima in an accumulator matrix.

## Results :

### Boundary tracing Results 


![Boundary tracing](https://user-images.githubusercontent.com/61361818/173068169-f3b57d95-e7df-425a-976d-3234ed15d645.PNG)


### Hough Transform Results 


![Hough transform](https://user-images.githubusercontent.com/61361818/173068285-7442b668-bdbd-4cba-8b0d-b8c1021923c1.PNG)

