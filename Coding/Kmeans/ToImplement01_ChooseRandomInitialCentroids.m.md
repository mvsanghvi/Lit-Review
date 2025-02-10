function arrCentroids = ToImplement01_ChooseRandomInitialCentroids(X, K)

% Purpose: choose random initial locations for the k means algorithm on the given data X

% Inputs:

% X ... an NxD 2D matrix containing the observed data. the measurements of each sample (row in X) is an D vector

% K ... an integer indicating the number of clusters to find in the data

% Outputs:

% arrCentroids ... a KxD matrix of K cluster centroids. The mean of the samples assigned to each cluster

% Preallocate the return array... always a good idea.

arrCentroids = zeros(K, size(X, 2)); % Why are we using size(X,2) here?

% @@@@@@@@@@@@@@@@@@ insert your code here @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

% Hint: choosing centroids from the samples tends to work well in practice.

% (Advanced: Can you explain why this works well compared to non-sample locations?)

%

r = randi(size(X,1),K,1);

arrCentroids = X(r,:);

end