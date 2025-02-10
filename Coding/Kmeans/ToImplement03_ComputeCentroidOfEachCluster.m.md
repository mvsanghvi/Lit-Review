function centroids = ToImplement03_ComputeCentroidOfEachCluster(X, idx, K)

% Purpose: compute new cluster centroid locations by calculating the mean of the samples assigned to each centroid.

% Inputs:

% X ... an NxD 2D matrix containing the observed data. the measurements of each sample (row in X) is an D vector

% idx .. a 1D array (Nx1) of cluster assignment for each of the N samples.

% Each entry in idx should be in the range [1..K]

% K ... a scalar, the number of clusters

% Outputs:

% centroids ... a KxD matrix of K cluster centroids. The mean of the samples assigned to each cluster

[n, d] = size(X); % get the # of samples and features (dimensions)

% Preallocate and then calcualte this return value in your code

centroids = zeros(K, d);

% @@@@@@@@@@@@@@@@@@ insert your code here @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

% Your task: For each centroid (e.g. the ith centroid), identify all points assigned to it, then

% compute the mean of those points and assign the mean to the ith row

% vector in centroids.

%

for i = 1 : K

temp = X((idx==i),:);

centroids(i,:) = mean(temp,1);

end