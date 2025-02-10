function plot2VarFunction(func,XRange, YRange,plotType)

% plot two variable function in 3D space for 'surf' visualization or in 2D

% space for 'contour' visualization

% Input

% func

% XRange [Xmin Xmax]

% YRange [Ymin Ymax]

% plotType default = 'surf', options: 'surf', 'contour'

% Output

% a figure with the proper visualization

%set default values for inputs

if ~exist('XRange', 'var')

XRange = [-1 1];

end

if ~exist('YRange', 'var')

YRange = [-1 1];

end

if ~exist('plotType', 'var')

plotType = 'surf';

end

%define the size of the grid for surf visualization

dX = 0.1;

dY = 0.1;

%plot the function

switch plotType

case 'surf'

%create a mesh for the surf. Otherwise it doesn't work

[X,Y] = meshgrid(XRange(1):dX:XRange(2),YRange(1):dY:YRange(2));

%calculate the value of a function for each point in 2D space

Z = func(X,Y);

surface(X,Y,Z)

view(3)

case 'contour'

fcontour(func, [XRange(1) XRange(2) YRange(1) YRange(2)]);

otherwise

disp('choose a plot type: surf or contour')

end