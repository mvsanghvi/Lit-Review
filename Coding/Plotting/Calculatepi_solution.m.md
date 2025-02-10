function pie = calculatePi_solution(n, figFlag)

%CALCULATEPI is a function to estimate pi using a randomized 'droplet fall' on circular area

%

% SYNTAX pie = calculatePi_solution(n, figFlag)

%

% INPUT n: integer representing number of "droplets"

% figFlag: (optional; default = true) logical value to turn figure

% on (true, 1) or off (false, 0)

%

% OUTPUT pie: estimated value of pi

%

% Example:

% myPi = calculatePi_solution(10000, false);

% The estimated value of Pi is 3.1400

%

% See also RECTANGLE, PLOT

% Qiongjing (Jenny) Zou, Feb 2023

% Srini Kota, Feb 2025

% Check for correct number of inputs (advanced writer)

if nargin == 1

figFlag = true; % Set default value for figFlag if not provided

elseif nargin == 2

if ~((islogical(figFlag) && isscalar(figFlag)) || ((isnumeric(figFlag) && isscalar(figFlag) && isequal(figFlag, 1) || isequal(figFlag, 0))))

error('figFlag must be a logical scalar or numeric 1 (true) or 0 (false).');

end

else

error("Invalid input arguments.")

end

% Check if input n is a positive integer scalar. (advanced writer)

if ~(isnumeric(n) && isscalar(n) && n > 0 && round(n) == n)

error("Invalid input of number of droplets.")

end

% Create a figure and draw a circle using rectangle function with Curvature property

fig = figure(); % create a new figure

hold on % hold the plot to add more elements later

plotOrRec = 'plot'; % choose 'plot' or 'rectangle' to draw graphics

% Note: switch-case is not necessnary for this function, but it is a nice

% feature to evaluate an expression and chooses to execute one of several groups of statements

switch plotOrRec % switch-case statements (advanced writer).

case 'plot'

% Define the coordinates of the box

x = [-1, 1, 1, -1, -1];

y = [-1, -1, 1, 1, -1];

% Plot the box

plot(x, y, '-b', 'LineWidth', 2)

axis equal; % set the aspect ratio to be equal in both x and y directions

% Define the center and radius of the circle

center = [0 0];

radius = 1;

% Create a vector of angles in radians from 0 to 2*pi with a small increment (1 radian = 180 degree / pi)

theta = linspace(0, 2*3.1416, 100);

% Compute the x and y coordinates of the circle's circumference

x = radius * cos(theta) + center(1); % cos (Cosine) takes argument in radians

y = radius * sin(theta) + center(2); % sin (Sine) takes argument in radians

% Plot the circle using the plot function

plot(x, y,'-r', 'LineWidth', 2);

case 'rectangle'

pos = [-1 -1 2 2]; % defining the square area in the form [x y w h]

rectangle('Position',pos,'Curvature',[1 1]) % draw the circle inside the square

axis equal % set the aspect ratio of the plot to be equal along both axes

rectangle('Position',pos,'EdgeColor','r') % draw the border of the square

end

% Add properties to figure (this part is optional)

xlim([-1.5, 1.5]);

ylim([-1.5, 1.5]);

% title('Calculate Pi');

xlabel('X');

ylabel('Y');

% Generate random x-, y- coordinates of "droplets" between -1 and 1

% (1) Generate random numbers between 0 and 1

x = rand(n,1);

y = rand(n,1);

% (2) Scale and shift the numbers to the desired range (-1 to 1)

x = -1 + 2*x; % numbers between -1 and 1

y = -1 + 2*y; % numbers between -1 and 1

% Initialize accumulator to zero for number of points inside circle

accumulator = 0;

% Loop through each point

for i = 1 : n

% Display point on figure if figFlag is true

if figFlag

figure(fig);

pause(0.001) % for Matlab OnDemand to do dynamic plotting

end

% check if the droplet falls inside the circle

if sqrt(x(i)^2+y(i)^2) <= 1

accumulator = accumulator + 1; % increment the accumulator

% plot the current droplet on figure

plot(x(i), y(i), 'r+')

else

% plot the current droplet on figure

plot(x(i), y(i), 'bd')

end

end

hold off % release the hold on the plot

% Calculate estimated pi value

totalArea = 2*2; % Area of square that encloses the circle

pie = totalArea*(accumulator/n);

title (['Total Droplets = ' num2str(n) ' , Droplets within circle = ' num2str(accumulator) ', Pi = ' num2str(pie)])

% Display the estimated value of pi. (this step is optional)

sprintf('The estimated value of Pi is %.4f', pie)

end