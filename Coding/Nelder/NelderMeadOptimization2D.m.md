function [xmin,fmin, IterationNum] = NelderMeadOptimization2D(func,X0,tol,MaxIter,plotFlag)

%NelderMeadOptimization2D minimize two variable func using NelderMead

%algorithm INPUT func func to be minimized X0 initial guess

%for parameters tol tolerance of func for the final

%simpleX(traingle) MaxIter maximum iteration number for loop plotFlag

%a flag to visualize the contour and simplex OUTPUT xmin optimized

%parameters fmin value of func at optmized parameters IterationNUm

%iteration number to reach tolerance

% define SimpleX parameters

alpha = 1; % reflection

beta = 2; % expansion

gamma = 0.5 ; % contraction

delta = 0.5; % shrinkage

%generate the initial simpleX(triangle)

simpleXSize = 0.05; % 0.05 might be better

simpleX = generateSimpleX_2D(X0,simpleXSize);

%calculate the vaule of function for all vertices in the simpleX

fvalue = nan(3,1);

for iDim = 1: 3 % 3 is the number of vertex in simpleX

fvalue(iDim) = func(simpleX(iDim,1), simpleX(iDim,2));

end

% create the contour before loop to avoid making in each iteration

if plotFlag

figure(1)

hold on

%set a range for parameters around the initial values for visualization

ARange = [X0(1)-10 X0(1)+10];

BRange = [X0(2)-10 X0(2)+10];

% make a mesh to create surf or contour

[A,B] = meshgrid(ARange(1):ARange(2) ,BRange(1):BRange(2) );

% calculate the value of loss function in parameter space

Z = func(A,B) ;

contour(A,B,Z)

end

% loop

IterationNum = 0;

while IterationNum < MaxIter

IterationNum = IterationNum + 1;

if plotFlag

h = plot([simpleX(:,1) ; simpleX(1,1) ], [simpleX(:,2) ; simpleX(1,2)], 'r' )

pause(0.1)

delete(h)

end

%sort/compare the function for all vertices (recognize u, v, w)

[~, indices] = sort(fvalue);

best = simpleX(indices(1),:); % coordinate of parameters

worst = simpleX(indices(end),:);

second_worst = simpleX(indices(end-1),:);

f_best = fvalue(indices(1)); % f_best = func(best(1), best(2))

f_worst = fvalue(indices(end));

f_second_worst = fvalue(indices(end-1));

%calcualte the reflection: both parameters and fvalue

average = mean(simpleX(indices(1:end-1),:)); % for higher dimension you should include all points up to worst one

reflection = average + alpha * (average - worst);

f_reflection = func(reflection(1), reflection(2));

% do expansion (do == replace the worst point with new point)

if f_reflection < f_best

expansion = average + beta *(reflection - average);

f_expansion = func(expansion(1), expansion(2));

if f_expansion < f_reflection

% accept exapnsion

simpleX(indices(end),:) = expansion;

fvalue(indices(end)) = f_expansion;

else

% keep reflection

simpleX(indices(end),:) = reflection;

fvalue(indices(end)) = f_reflection;

end

% do reflection

elseif f_reflection <= f_second_worst && f_reflection >= f_best

% accept reflection

simpleX(indices(end),:) = reflection;

fvalue(indices(end)) = f_reflection;

% check outside contraction

elseif f_reflection > f_second_worst && f_reflection < f_worst

Contraction_out = average + gamma* (reflection - average);

f_Contraction_out = func(Contraction_out(1), Contraction_out(2));

if f_Contraction_out < f_reflection

%accept contration out

simpleX(indices(end),:) = Contraction_out;

fvalue(indices(end)) = f_Contraction_out;

end

% check inside contraction

elseif f_reflection >= f_worst

Contraction_in = average +gamma*(worst - average);

f_Contraction_in = func(Contraction_in(1), Contraction_in(2));

if f_Contraction_in < f_worst

%accept inside contraction

simpleX(indices(end),:) = Contraction_in;

fvalue(indices(end)) = f_Contraction_in;

% do shrinkage

else

for iVertex = 2:3 % triangle

simpleX(indices(iVertex,:)) = simpleX(indices(1,:)) + delta* (simpleX(indices(iVertex,:)) - simpleX(indices(1,:)));

fvalue(indices(iVertex)) = func(simpleX(indices(iVertex,1)), simpleX(indices(iVertex), 2));

end

% % for higher dimension you should use this version

% for iVertex = 2:size(simpleX, 1)

% simpleX(indices(iVertex,:)) = simpleX(indices(1,:)) + delta* (simpleX(indices(iVertex,:)) - simpleX(indices(1,:)));

% fvalue(indices(iVertex)) = func(simpleX(indices(iVertex,1)), simpleX(indices(iVertex), 2));

% end

end

end

% check convergence

if abs(fvalue(indices(end)) - fvalue(indices(1))) < tol

break;

end

end

xmin = simpleX(indices(1),:);

fmin = fvalue(indices(1));

if IterationNum == MaxIter

warning('The algorithm reaches the maximum iteration number, you may consider higher values for MaxIter as an input')

end

end