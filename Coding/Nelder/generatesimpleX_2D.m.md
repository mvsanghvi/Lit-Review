function [simpleX] = generateSimpleX_2D(X0,simpleXSize)

%generateSimpleX generates a simplex which is a triangle in 2 dimension

% INPUT

% X0 initial point

% simpleSize size of simpleX (triangle in 2D)

% OUPUT

% simpleX a matrix of vertices of simpleX (triangle in 2D)

%

% find the triangle vertices , simpleX

simpleX = nan(3,2);

simpleX(1,:) = [X0(1) X0(2)];

simpleX(2,:) = [X0(1)-simpleXSize X0(2)];

simpleX(3,:) = [X0(1) X0(2)-simpleXSize];

end