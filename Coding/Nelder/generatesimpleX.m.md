function simpleX= generateSimpleX_N(X0, sizeSimpleX)

% generates a simpleX polygon for initializing the Nelder-Mead algorithm

% Input

% X0 initial point, horizental vector [1 x N]

% sizeSimpleX length of polygon side

% Output

% simpleX (N+1, N) metric consisting of vertex coordinate for a polygon in N space

%set a default value for size of the SimpleX

if ~exist('sizeSimpleX','var')

sizeSimpleX = 0.05;

end

%define the dimension of space for a given function

N = numel(X0);

% initialize the SimpleX metric

simpleX = ones(N+1, N).*X0; % it should be N+1 vertices that each has a N dimension

% step away from the initial position in each space direction. sizeSimplex

% is the size of polygon side

for iDim = 2: N+1

simpleX(iDim, iDim - 1) = simpleX(iDim,iDim -1) + sizeSimpleX;

end