# ImageProcessing

# Question 1: Implement Simulation and Display of an Image, Negative of an Image (Binary & Grayscale) Using MATLAB

This MATLAB program demonstrates how to simulate and display the negative of an image in both color (binary) and grayscale formats.

## MATLAB Code:

```matlab
% Read an image
img = imread('img1.png');  % Replace 'img1.png' with your image file name

% Display the original image
imshow(img);
title('Original Image');

% Generate the negative of the image
neg_img = 255 - img;

% Display the negative image
figure;
imshow(neg_img);
title('Negative Image');

% Convert the original image to grayscale
gray_img = rgb2gray(img);

% Generate the negative of the grayscale image
neg_gray_img = 255 - gray_img;

% Display the negative grayscale image
figure;
imshow(neg_gray_img);
title('Negative Grayscale Image');
