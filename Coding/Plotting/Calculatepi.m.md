function pie = calculatePi(n, figFlag)

%CALCULATEPI is a functions to visualize the estimation of pi using a randomized 'droplet

%fall' on a cirular area

%

% SYNTAX pie = calculatePi(n, figFlag)

%

% INPUT n: positive integer representing total number of 'droplets'

% figFlag: (optional, default is true) logical value to turn figure

% on (true or 1) or off (false or 0)

%

% OUPUT pie: estimated value of pi

%

% Example:

% pie = calculatePi(10000, false);

%

% See also PLOT

% Author name, date

% Set default value for figFlag if not provided.

if nargin == 1

figFlag = true;

end

% Create a figure and draw a box and an enclosed circle

fig = figure();

hold on % (add later)

% draw a square

x = [-1 , 1, 1, -1, -1];

y = [-1, -1, 1, 1, -1];

plot(x, y, '-r', 'LineWidth', 2) % (spend some time to explain LineSpec — Line style, marker, and color)

% draw a circle

alpha = linspace(0, 2*3.1416, 100); % (intro linspace); create a vector of angle from 0 to 2pi with evenly speaced small interval

x = cos(alpha); % (why do I use the same varialble names x and y as above?)

y = sin(alpha);

plot(x,y, '-b', 'LineWidth', 2); % (What went wrong? without 'hold on')

axis equal % set the aspect ratio to be equal in both x and y directions

% Add properties to the plot (optional) (% check bottom of plot help page)

xlim([-1.5, 1.5]);

ylim([-1.5, 1.5]);

title('Calculate Pi');

xlabel('X');

ylabel('Y');

% Generate random x-, y- coordinates of "droplets" between -1 and 1

% help rand, to see the equation: n random numbers in the interval (a,b) with the formula r = a + (b-a).*rand(n,1).

x = -1 + 2*rand(n,1);

y = -1 + 2*rand(n,1); % (why do I use the same varialble names x and y as above?)

% % Or do it in 2 steps:

% % (1) Generate random numbers between 0 and 1

% x = rand(n, 1); % (try rand(2), rand(2,1))

% y = rand(n, 1); % (why do I use the same varialble names x and y as above?)

% % (2) Scale and shift the numbers to -1 to 1

% x = -1 + 2*x;

% y = -1 + 2*y;

% Initialize the accumulator to zero

accumulator = 0;

% Loop throught each point from 1 to n

for i = 1 : n

% to plot the points on the figure

if figFlag

figure(fig)

pause(0.001) % for Matlab OnDemand to do dynamic plotting

end

% (1) plot the point on the figure

plot(x(i), y(i), '+')

% (2) calculate the accumulator if the points falls inside or on the circle

if sqrt(x(i)^2+y(i)^2) <= 1

accumulator = accumulator + 1;

end

end

% Calculate pi

totalArea = 2*2;

pie = totalArea*accumulator/n;

sprintf('The estimated value of Pi is %.4f', pie)

end