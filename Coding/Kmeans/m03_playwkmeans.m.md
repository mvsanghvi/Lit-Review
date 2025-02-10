% play calls

% init

% run

% plotKMeansState calls

% plotSamples

% drawArrow .. This could be optional, it would be nice to have voronoi

% Purpose of this program is to allow you to play with the k-means algorithm that you have now implemented.

%

% This file does the following steps:

% 1. loads the data containing the measurments of the samples in your study

% 2. Initialzes the cluster centers

% 3. Applies the k-means algorithm to cluster the samples into the number of groups you specify

% It does this by calling the m01_runkMeans.m file which in turn calls the core functions you have implemented.

% It also calls helperFunctions to display the algorithms state at each iteration.

% Initialization: its a good idea to start from a clean slate

clear ; % clear varaibles from memory

close all; % close all open figure windows

clc % clear the command window

% K-Means parameters

% =======================

nClusterCountK = 3; % Default is 3, also try 2,4,6

nMaxIterations = 10; % Default is 10, Tip try playing with fewer and more max iterations

nMaxExperiments=1; % Default is 1, try 10

bPause=false; % toggle pausing the code on or off (true or false)

bUseRandomInitialization=false; % default is false, try true

fprintf('Play with the K-means algorithm you have now implemented.\n');

% Load example dataset

S=load('data_kmeans_cloudOfPoints.mat'); % 300 datapoints (x,y) from 3 clusters into array X

X=S.X; % to avoid contaminating our name space we load into struct S, then copy the part that we need.

for i=1:nMaxExperiments

fprintf('\n ---- Running experiment %d. \n',i);

% For consistency, here we set centroids to specific values

% but in practice you want to generate them automatically, such as by

% settings them to be random examples (as can be seen in kMeansInitCentroids).

if bUseRandomInitialization

arr2DInitialCentroids = ToImplement01_ChooseRandomInitialCentroids(X,nClusterCountK);

else

arr2DInitialCentroids = [3 3; 6 2; 8 5];

end

% arr2DInitialCentroids = [2.5 2.5; 6.5 2.5; 7 4];

% hold on

% plot(centroids(:,1), centroids(:,2), 'x', ...

% 'MarkerEdgeColor','k', ...

% 'MarkerSize', 10, 'LineWidth', 3);

% Run K-Means algorithm. The 'true' at the end tells our function to plot

% the progress of K-Means

brunkMeansWithPauseAtIterations=~bUseRandomInitialization;

[centroids, arr1Didx] = m01_runkMeans(X, arr2DInitialCentroids, nMaxIterations, true, brunkMeansWithPauseAtIterations);

fprintf('K-Means Done.\n');

if bPause

fprintf('Program paused. Press enter to continue.\n');

pause;

end

end

fprintf('main_kmeans program completed. \n');

fprintf('Centroids computed: \n')

display(centroids)

fprintf('############################\n')