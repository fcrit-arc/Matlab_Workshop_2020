# Matlab Workshop

- Import and Export image
```matlab
% read image
img = imread('nature.jpg');

% RGB to Black and white
img = rgb2gray(img);

% about image
whos img
imfinfo('car_view.jpg')

% show image
figure; imshow(img)
title('Original image')
figure; imhist(img)
title('Original image histogram')

% Histogram equalization...we will come to it later
img = histeq(img);

% show image
figure; imshow(img)
title('Equalized image')
figure; imhist(img)
title('Equalized image histogram')

% export image
imwrite (img,'nature_histeq.jpg');
```
---
- Image conversion
```matlab
% read image
img = imread('peppers.png');

% image conversion
% RGB to BW
bw = rgb2gray(img);
figure; imshowpair(img,bw,'montage');
title('Original image with Black and White image');

[r,g,b] = imsplit(img);
figure; montage({r,g,b},'Size',[1 3]);
title('Red, Green and Blue components');

% RGB to HSV
hsv = rgb2hsv(img);

[h,s,v] = imsplit(hsv);
figure; montage({h,s,v},'Size',[1 3]);
title('Hue, Saturation and color values');
```
---
- Image binarization
```matlab
% read image
img = rgb2gray(imread('num_plate.jpg'));

% binarize
BW = imbinarize(img);
% binarize with threshold 50%
BWthr = imbinarize(img,0.5);
% binarize adaptively
BWadap = imbinarize(img,'adaptive');

% show
figure; imshowpair(img,BW,'montage');
figure; imshowpair(img,BWthr,'montage');
figure; imshowpair(img,BWadap,'montage');
```
---
- Generic transformations
```matlab
I = imread('cameraman.tif');
imshow(I)
tform = affine2d([1 0 0; .5 1 0; 0 0 1])
J = imwarp(I,tform);
figure
imshow(J)
```