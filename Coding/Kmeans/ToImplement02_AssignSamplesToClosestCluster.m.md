function idx = ToImplement02_AssignSamplesToClosestCluster(X, centroids)

% Purpose: computes the centroid memberships for every sample

% Inputs:

% X ... an NxD 2D matrix containing the observed data. the measurements of each sample (row in X) is an D vector

% centroids ... a KxD matrix of K cluster centroids

% Outputs:

% idx .. a 1D array (Nx1) of cluster assignment for each of the N samples.

% Each entry in idx should be in the range [1..K]

%

% good practice is to preallocate K. Do you recall why ?

K = size(centroids, 1);

% You need to return the following variables correctly.

idx = zeros(size(X,1), 1);

% @@@@@@@@@@@@@@@@@@ insert your code here @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

% Instructions: For each sample, find the closest centroid, and record this

% in the array, idx, at the right location.

%

for i = 1 : size(X,1)

temp = NaN(1, K);

for j = 1 : K

temp(j) = norm(X(i,:) - centroids(j,:));

end

idx(i,1) = find(min(temp) == temp);

end