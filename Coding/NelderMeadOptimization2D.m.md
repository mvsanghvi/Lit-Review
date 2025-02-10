function [xmin, fmin, iterationNum] = NelderMeadOptimization2D(func, X0, tol, MaxIter, plotFlag)

%NelderMeadOptimization2D minimize two variable function using Nelder Mead

%algorithm

%INPUT:

%func function to be minimized

%X0 initial guess for parameters

%tol tolerance of the function for the final simplex(triangle)

%MaxIter maximum interation number for loop

%plotFlag a flag to visualize the contour and simplex

%OUTPUT:

%xmin optimized parameters

%fmin value of func at optmized parameters

%iterationNum iteration number to reach tolerance

%Define simplex parameters

alpha = 1; %reflection

beta = 2; %expansion

gamma = 0.5; %contraction

delta = 0.5; %shrinkage

%Step 1: Make our triangle (generate the intial simplex)

simplexSize = 1;

simplex = generateSimplex_2D(X0, simplexSize);

%Step 2: Calculate f values (value of function for all vertices of

%triangle/simplex)

fvalue = nan(3,1);

for iDim = 1 : 3

fvalue(iDim) = func(simplex(iDim, 1), simplex(iDim, 2));

end

%create the contour before loop

figure(1)

hold on

Arange = [X0(1)-10 X0(1)+10];

Brange = [X0(2)-10 X0(2)+10];

z= func(A,B);

countour (A,B,z)

%Make our loop:

iterationNum= 0;

while iterationNum < MaxIter

iterationNum = iterationNum +1;

if plotFlag

plot([simplex(:,1);simplex(1,1)], [simplex(:,2);simplex(1,2)])

end

%Step 3: Compare the vertices (Sort the function for all vertices(recovnize u,v, w))

[~,indices] = sort(fvalue);

best = simplex(indices(1));%coordinate of parameters

worst = simplex(indices(end));

second_worst = simplex(indices(end-1));

f_best= fvalue(indices(1));

f_worst = fvalue(indices(end));

f_second_worst = fvalue(indices(end-1));

%Step 4: Compute reflection: both paramters and fvalue

Xo= mean(simplex(indices(1:end-1, :)));

reflection = Xo + alpha * (Xo- worst);

f_reflection = func(Xo(1), Xo(2));

%Step 5: Do expansion (replace the worst point with new point)

if f_reflection <= f_best

expansion = Xo + beta *(reflection - Xo);

f_expansion = func(expansion(1), expansion(2));

if f_reflection > f_expansion

%accept expansion

simplex(indices(end),:) = expansion;

fvalue(indices(end)) = f_expansion;

else

simplex(indices(end),:) = reflection;

fvalue(indices(end)) = f_reflection;

end

%Step 6: Do reflection

elseif f_reflection > f_best && f_reflection < f_second_worst

%accept relfection

simplex(indices(end),:) = reflection;

fvalue(indices(end)) = f_reflection;

%Step 7: If not satisfied, do outside contraction, then inside contraction,

%then shrinkage

elseif f_reflection >= f_second_worst && f_reflection < f_worst

outside_contraction = Xo + gamma * (reflection- Xo);

f_ocontraction = func(outside_contraction(1), outside_contraction(2));

if f_reflection > f_ocontraction

%accept outside contraction

simplex(indices(end),:) = outside_contraction;

fvalue(indices(end)) = f_ocontraction;

end

elseif f_reflection >= f_worst

inside_contraction = Xo + gamma * (worst- Xo);

f_icontraction = func(inside_contraction(1), inside_contraction(2));

if f_icontraction < f_worst

%accept inside contraction

simplex(indices(end),:) = inside_contraction;

fvalue(indices(end)) = f_icontraction;

end

else

for ivertex = 2:3

simplex(indices(ivertex,:))= simplex(indices(1,:))+ delta*(simplex(indices(ivertex,:))-simplex(indices(1,:)));

fvalue(indices(ivertex))=

end

%check convergence

if fvalue(indices(end))- fvalue(indices(1)) <tol

break;

end

end

xmin = simplex(indices(1),:);

fmin = fvalue(indices(1));

if iterationNum== MaxIter

warning ('The algorith reaches the maximum iteration number, you may consider higher values for MaxIter as an input')

end

end