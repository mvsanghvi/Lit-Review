function[simplex]=generateSimplex_2D(X0,simplexSize)

%generateSimplex generates a simplex which is a triangle in 2D

%Input:

%x0 Initial point

%simplexSize size of simplex (triangle in 2D)

%Output:

%simplex a matrix of verticed of simples (triangle in 2D)

a0 = X0(1);

b0 = X0(2);

%find the triangle vertices, simplex

simplex = nan(3,2);

simplex(1,:) = [X0(1),X0(2)];

simplex(2,:) = [X0(1)-simplexSize,X0(2)];

simplex(3,:) = [X0(1),X0(2)-simplexSize];

end