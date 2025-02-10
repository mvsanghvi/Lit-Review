%assignment 1: visualizing the function

close all

clear

%task 1: surf visualization for a single minimum function

a0 = 1;

b0 = 3;

func = @(a,b) (a- a0).^2 + (b - b0).^2;

ARange = [-10 10];

BRange = [-10 10];

plotType = 'surf';

[X,Y] = meshgrid(ARange(1):ARange(2),BRange(1):BRange(2));

%calculate the value of a function for each point in 2D space

Z = func(X,Y);

figure;

surface(X,Y,Z)

view(3)

% figure

% plot2VarFunction(func,XRange, YRange,plotType)

xlabel('X')

ylabel('Y')

zlabel('function')

%task 2: contour visualization for a single minimum function

a0 = 1;

b0 = 3;

func = @(a,b) (a- a0).^2 + (b - b0).^2;

ARange = [-10 10];

BRange = [-10 10];

plotType = 'contour';

figure;

fcontour(func, [ARange(1) ARange(2) BRange(1) BRange(2)]);

%

% figure

% plot2VarFunction(func,XRange, YRange,plotType)

xlabel('X')

ylabel('Y')

% task 3: test for another function with more than one local minumums

% Himmelblau's function

a0 = 11;

b0 = -7;

func2 = @(a,b) (a.^2 + b - a0).^2 + (a + b.^2 -b0).^2;

ARange = [-4 4];

BRange = [-4 4];

plotType = 'surf';

figure

plot2VarFunction(func,ARange, BRange,plotType)

xlabel('X')

ylabel('Y')

zlabel('function')

plotType = 'contour';

figure

plot2VarFunction(func,ARange, BRange,plotType)

xlabel('X')

ylabel('Y')

zlabel('function')