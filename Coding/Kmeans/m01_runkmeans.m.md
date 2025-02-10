function [arr2DCentroids, arr1DClusterAssignment] = m01_runkMeans(arr2DX, arr2DInitialcentroids, ...

nMaxIterations, bPlotProgress, bPauseBtwnIterations)

% Purpose: runs the K-Means algorithm on the given 2D data matrix arr2DX,

%

% inputs

% arr2DX ... the given 2D data matrix: each row of arr2DX is a single example, the columns of arr2DX are the features

% nNumSamples x nNumFeatures matrix where nNumSamples is the number of samples, and nNumFeatures is number of features.

% arr2DInitialcentroids .... are the initial cluster centers.

% K x nNumFeatures matrix where K is the number of clusters to find.

% nMaxIterations ... is the maximum number of iterations of K-Means to execute.

% A scalar integer >0

% bPlotProgress is a boolean true/false flag that indicates whether the function should also plot its progress as the

% learning happens. This is set to false by default.

%

% bPauseBtwnIterations is a boolean indicating whether to pause after each iteration

%

% Outputs:

% arr2DCentroids ... a K by nNumFeatures matrix of the computed arr2DCentroids

% arr1DClusterAssignment ... a nNumSamples x 1 vector listing the cluster number (group) that each sample was assigned to (i.e. each entry in range [1..K])

% nNumSamples is the number of samples.

%

% Set default value for plot progress

if ~exist('bPlotProgress', 'var') || isempty(bPlotProgress)

bPlotProgress = false;

end

% Plot the data if we are plotting progress

if bPlotProgress

figure;

hold on;

end

% Initialize values

[nNumSamples nNumFeatures] = size(arr2DX);

K = size(arr2DInitialcentroids, 1);

arr2DCentroids = arr2DInitialcentroids;

previous_centroids = arr2DCentroids;

arr1DClusterAssignment = zeros(nNumSamples, 1);

% Run K-Means

for i=1:nMaxIterations

% Output progress

fprintf('K-Means iteration %d/%d...\n', i, nMaxIterations);

% For each example in arr2DX, assign it to the closest centroid

arr1DClusterAssignment = ToImplement02_AssignSamplesToClosestCluster(arr2DX, arr2DCentroids); % @@@@

% Optionally, plot progress here

if bPlotProgress

plotkMeansState(arr2DX, arr2DCentroids, previous_centroids, arr1DClusterAssignment, K, i, nMaxIterations);

previous_centroids = arr2DCentroids;

drawnow;

if bPauseBtwnIterations

fprintf('Press enter to continue.\n');

pause;

end

end

% Given the memberships, compute new arr2DCentroids

arr2DCentroids = ToImplement03_ComputeCentroidOfEachCluster(arr2DX, arr1DClusterAssignment, K); % @@@@

end

% Hold off if we are plotting progress

if bPlotProgress

hold off;

end

end