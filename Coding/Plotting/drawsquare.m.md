% draw afunction [count,p] = myFactorial(Frank,t)

function [count,my_value_of_pi] = drawSquare(n)

% clear all

% close all

x = [-1,1,1,-1,-1];

y = [-1,-1,1,1,-1];

%n = 100

figure, plot(x,y, '-b')

xlim([-1.5 1.5])

ylim([-1.5 1.5])

theta = linspace(0,2*pi,100);

x2 = cos(theta);

y2 = sin(theta);

hold on, plot(x2,y2,'b')

%generate n random numbers between -1, 1 (both x and y)

x3 = 2*rand(1,n) - 1;

y3 = 2*rand(1,n) - 1;

hold on, plot(x3,y3,'p')

count = 0

tic

for i=1:length(x3)

if x3(i).^2 + y3(i).^2 <= 1

count = count + 1

pause(0.001)

end

end

toc

count

tic

Rsquare = x3.^2 + y3.^2;

count1 = length(find(Rsquare < 1))

toc

%pi value

side = abs(min(x)) + abs(max(x))

area = side.^2

circleAreaWOpi = (cos(max(theta))).^2

my_value_of_pi = count*area./(circleAreaWOpi.*n)

my_value_of_pi