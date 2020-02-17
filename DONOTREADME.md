# Matlab Workshop

- Import and Export image
```matlab
% read image - write your code here
%%

%%

% RGB to Black and white
img = rgb2gray(img);

% about image - write your code here
%%

%%

% show image - write your code here
%%

%%

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
%%

%%

% image conversion
% RGB to BW - write your code here
%%

%%

figure; imshowpair(img,bw,'montage');
title('Original image with Black and White image');

[r,g,b] = imsplit(img);
figure; montage({r,g,b},'Size',[1 3]);
title('Red, Green and Blue components');

% RGB to HSV
%%

%%

% Split image to components - write your code here
%%

%%

figure; montage({h,s,v},'Size',[1 3]);
title('Hue, Saturation and color values');
```
---
- Image binarization
```matlab
% read image
img = rgb2gray(imread('num_plate.jpg'));

% binarize - write your code here
%%

%%

% binarize with threshold 50% - write your code here
%%

%%

% binarize adaptively - write your code here
%%

%%

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

% affine transform - write your code here
%%

%%

% apply transform - write your code here
%%

%%
figure
imshow(J)
```