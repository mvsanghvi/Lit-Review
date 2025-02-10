%assignment2: visualize a polygon on contour for a given function

close all

clear

% addpath('')

%task 1: contour visualization for a single minimum function

% define the loss function that we need to optimize

a0 = 1;

b0 = 3;

func = @(a,b) (a- a0).^2 + (b - b0).^2;

ARange = [-10 10];

BRange = [-10 10];

plotType = 'contour';

figure

plot2VarFunction(func,ARange, BRange,plotType)

xlabel('X')

ylabel('Y')

% task 2: choose a point within given XRange and YRange and plot them

x0 = 0;

b0 = 0;

hold on

plot(x0,b0,'*k')

% task 3: generate the initial SimpleX - typical way using in Nelder_mead

% algorithm

% SimpleX for 2-variable function is a triangle

X0 = [x0, b0];

sizeSimpleX = 0.5;

simpleX= generateSimpleX(X0, sizeSimpleX)

% task 4: plot the SimpleX on contour

vertex_X = [simpleX(:,1) ; simpleX(1,1)];

vertex_Y = [simpleX(:,2) ; simpleX(1,2)];

plot(vertex_X,vertex_Y)

% task 5 (optional): choose a random point for given XRange and YRange and

% repeat task 3 and task 4

a0 = ARange(1) + rand()* abs(ARange(2)- ARange(1));

b0 = BRange(1) + rand()* abs(BRange(2)- BRange(1));

%task 3 & 4

X0 = [a0, b0];

sizeSimpleX = 0.5;

simpleX= generateSimpleX(X0, sizeSimpleX)

vertex_X = [simpleX(:,1) ; simpleX(1,1)];

vertex_Y = [simpleX(:,2) ; simpleX(1,2)];

plot(vertex_X,vertex_Y)