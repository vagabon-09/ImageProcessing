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

```

# Question 2: Implementation of Relationships between Pixels Using MATLAB

This MATLAB program demonstrates how to access and manipulate pixel values, as well as perform neighborhood operations on an image.

## MATLAB Code:

```matlab
% Read an image
img = imread('img1.png');  % Replace 'img1.png' with your image file name

% Accessing pixel values
pixel_value = img(100, 150);  % Access the pixel value at row 100, column 150

% Display the pixel value (for demonstration purposes)
disp(['Pixel Value at (100,150): ', num2str(pixel_value)]);

% Neighborhood operations
% Extracting a 21x21 neighborhood centered at (100, 150)
neighborhood = img(90:110, 140:160);

% Display the neighborhood
imshow(neighborhood);
title('Neighborhood');

```

# Question 3: Histogram Mapping and Equalization for an Image

This MATLAB program demonstrates how to perform histogram mapping and histogram equalization on an image to enhance its contrast.

## MATLAB Code:

```matlab
% Read an image
img = imread('img1.png');  % Replace 'img1.png' with your image file name

% Convert the image to grayscale if it's a color image
gray_img = rgb2gray(img);

% Display the original grayscale image
figure;
imshow(gray_img);
title('Original Grayscale Image');

% Calculate the histogram of the original image
[original_hist, bin_edges] = histcounts(gray_img, 256);

% Plot the histogram of the original image
figure;
bar(bin_edges(1:end-1), original_hist, 'histc');
title('Original Histogram');
xlabel('Pixel Intensity');
ylabel('Frequency');

% Histogram Equalization
eq_img = histeq(gray_img);

% Display the equalized image
figure;
imshow(eq_img);
title('Equalized Image');

% Calculate the histogram of the equalized image
[eq_hist, ~] = histcounts(eq_img, 256);

% Plot the histogram of the equalized image
figure;
bar(bin_edges(1:end-1), eq_hist, 'histc');
title('Equalized Histogram');
xlabel('Pixel Intensity');
ylabel('Frequency');

```


# Question 4: Write a program in MATLAB for image smoothing and sharpening for an image.

## Answer:

```matlab
% Read an image
img = imread('img1.png');  % Replace 'img1.png' with your image file name

% Smoothing using Averaging Filter
smooth_img = imfilter(img, fspecial('average', 3));  % Apply 3x3 averaging filter

% Sharpening using Laplacian Filter
sharp_img = imfilter(img, fspecial('laplacian'));  % Apply Laplacian filter for sharpening

% Display the original and smoothed image
figure;
imshowpair(img, smooth_img, 'montage');
title('Original and Smoothed Images');

% Display the original and sharpened image
figure;
imshowpair(img, sharp_img, 'montage');
title('Original and Sharpened Images');

