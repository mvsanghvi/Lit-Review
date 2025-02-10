% Purpose of this program is to help you write the 3 core functions that

% are needed to build a k-means program.

%

% Empty shells of these functions have been started for you in the following 3 files

% that you are to implement fully:

% 1. ToImplement01_ChooseRandomInitialCentroids.m ... make an initial guess of the cluster centers

% 2. ToImplement02_AssignSamplesToClosestCluster.m ... assign each sample to one cluster (group)

% 3. ToImplement03_ComputeCentroidOfEachCluster.m ... calculate the center of each group

% Initialization: its a good idea to start from a clean slate

clear ; % clear varaibles from memory

close all; % close all open figure windows

clc % clear the command window

% K-Means parameters

% =======================

% Select an initial set of centroids

nClusterCountK = 3; % assume there are 3 clusters, , also try 2,4,6

% % Choosing nClusterCount? Problem domain knowledge or Try interrogating the data

% % explore data first. Always a good idea.

% hist(X(:,1),100); % not too revealing... unimodal?

% hist(X(:,2),100); % trimodal.. Hmmm might tell us something..

bPause=false; % toggle pausing the code on or off (true or false)

% Load example dataset

S=load('data_kmeans_cloudOfPoints.mat'); % 300 datapoints (x,y) from 3 clusters into array X

X=S.X; % to avoid contaminating our name space we load into struct S, then copy the part that we need.

nNumFeatures=size(X,2);

figure;

scatter(X(:,1), X(:,2), 15)

%% ============= Step 1) Choose randomly K samples as the initial centers of the K clusters

fprintf('Step 1) Choose K samples at random from the rows of X as the initial centers of the K clusters.\n');

arrTestCentroids=ToImplement01_ChooseRandomInitialCentroids(X, nClusterCountK);

fprintf('Size of arrTestCentroids should be %d by %d. \n', nClusterCountK, nNumFeatures );

fprintf('Yours arrTestCentroids is of size %d by %d. \n', size(arrTestCentroids,1), size(arrTestCentroids,2));

% % Insert code to verify rows of arrTestCentroids are in X

% bInitialCentersAreOK=true;

% for i=1:nClusterCountK

% pt=arrTestCentroids(i,:);

%

% bFound=false;

% for k=1:size(X,1)

% bFound2=false;

% for j=1:nNumFeatures

% end

% end

%

% end

%% ============= Step 2) Assign samples to closest cluster centroid

fprintf('Step 2) Assign samples to closest cluster centroid.\n');

arr2DInitialCentroids = [3 3; 6 2; 8 5]; % Now we will fix the cluster centers

% if bUseRandomInitialization

% arr2DInitialCentroids = ChooseRandomInitialCentroids(X,nClusterCountK);

% end

% Find the closest centroids for the examples using our initial guess arr2DInitialCentroids

arr1Didx = ToImplement02_AssignSamplesToClosestCluster(X, arr2DInitialCentroids);

fprintf('Closest centroids for the first 3 examples: \n')

fprintf(' %d', arr1Didx(1:3));

fprintf('\n(the closest centroids should be 1, 3, 2 respectively)\n');

if bPause

fprintf('Program paused. Press enter to continue.\n');

pause;

end

%% ============= step 3) Compute centroid of each cluster

%

fprintf('\nstep 2) Compute centroid of each cluster.\n');

% Compute means based on the closest centroids found in the previous part.

centroids = ToImplement03_ComputeCentroidOfEachCluster(X, arr1Didx, nClusterCountK);

fprintf('Centroids computed after first iteration of the algorithm: \n')

fprintf(' %f %f \n' , centroids');

fprintf('(the centroids should be\n');

fprintf(' [ 2.428301 3.157924 ]\n');

fprintf(' [ 5.813503 2.633656 ]\n');

fprintf(' [ 7.119387 3.616684 ]\n');

if bPause

fprintf('Program paused. Press enter to continue.\n');

pause;

end