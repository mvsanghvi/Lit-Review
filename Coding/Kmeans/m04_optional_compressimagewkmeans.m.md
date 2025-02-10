% Purpose of this program is to challenge your thinking about how k-means can be useful.

% There are many ways in which a clustering can be useful.

% An image for example can be compressed to a smaller size (Saving time to load it, saving disk space or computer

% memory to store it) by determining a smaller number of colors or gray levels at which the image can

% still be faithfully represented.

% This exercise is optional.

% Those of you with more advanced programming skills are welcome to examine this program.

% Several images have been provided in the \data directory for you to play with.

% See how well the k-means algorithm can compress one or more of these provided images.

% Then try it on an image of your own, e.g. a selfie -- if you are into that.. :-)

%% Optional challenge: Apply k-means to compress a brain image (susceptibility weighted image that can reveal

% microbleeds)

% In this exercise, you will use K-Means to compress an image. To do this,

% you will first run K-Means on the colors of the pixels in the image and

% then you will map each pixel on to it's closest centroid.

%

% Initialization: its a good idea to start from a clean slate

clear ; % clear varaibles from memory

close all; % close all open figure windows

clc % clear the command window

% bPause=false; % toggle pausing the code on or off (true or false)

strImageFileName='SusceptibilityWeightedImage_7T.jpg';

% strImageFileName='Rainbow.jpg';

% strImageFileName='DiffusionMRI_Tractogram.png';

% strImageFileName='PerfusionMRI_PediatricBrainTumor.jpg';

fprintf('Optional challenge: Apply k-means to compress an image.\n');

% Load an image

A = double(imread(strImageFileName));

% If imread does not work for you, you can try instead

% load ('bird_small.mat');

A = A / 255; % Divide by 255 so that all values are in the range 0 - 1

% Size of the image

img_size = size(A);

% Reshape the image into an Nx3 matrix where N = number of pixels.

% Each row will contain the Red, Green and Blue pixel values

% This gives us our dataset matrix X that we will use K-Means on.

X = reshape(A, img_size(1) * img_size(2), 3);

% Run your K-Means algorithm on this data

% You should try different values of K and max_iters here

nClusterCountK = 16;

max_iters = 10;

% When using K-Means, it is important the initialize the centroids

% randomly.

% You should complete the code in ChooseRandomInitialCentroids.m before proceeding

arr2DInitialCentroids = ToImplement01_ChooseRandomInitialCentroids(X, nClusterCountK);

% Run K-Means

[centroids, arr1Didx] = m01_runkMeans(X, arr2DInitialCentroids, max_iters);

% Finding the closest cluster members

% arr1Didx is the listing the cluster number (group) that each sample was assigned to

% Essentially, now we have represented the image X as in terms of the

% indices in idx.

% We can now recover the image from the indices (idx) by mapping each pixel

% (specified by it's index in idx) to the centroid value

X_recovered = centroids(arr1Didx,:);

% Reshape the recovered image into proper dimensions

X_recovered = reshape(X_recovered, img_size(1), img_size(2), 3);

% Display the original image

subplot(1, 2, 1);

imagesc(A);

title('Original');

% Display compressed image side by side

subplot(1, 2, 2);

imagesc(X_recovered);

set(gcf,'position', [ 674 456 1015 420]);

title(sprintf('Compressed, with %d colors or gray levels.', nClusterCountK));

fprintf('Note the original SWI image required 24bits/pixel, compressed image requires only 4 (plus small lookup table); nearly 87%% compression.\n');