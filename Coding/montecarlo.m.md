%set function

function[pi1, count]= montecarlo(n)

%set coordinates of a square

%include first coordinates at end again to close the square

x = [-1, -1, 1, 1, -1];

y = [-1, 1, 1, -1, -1];

% draw the square

plot(x,y,'r')

xlim([-1.5, 1.5])

ylim([-1.5, 1.5])

%set data points of circle within the square

theta = linspace(0, 2*pi, 100);

a = cos (theta);

b = sin(theta);

%plot the circle

plot(a,b,'b');

xlim([-1.5, 1.5])

ylim([-1.5, 1.5])

%plot both

hold on

plot(x,y,'r');

plot(a,b,'g');

xlim([-1.5, 1.5])

ylim([-1.5, 1.5])

%generate n random numbers between -1 to 1

c= 2*rand(100,1)-1;

d= 2*rand(100,1)-1;

%confirm values are between -1 to 1

min(c)

max(c)

min(d)

max(d)

%plot random numbers

%plot(c,d, "bo");

%check if points fall within circle of radius 1 using the condition:

%x^2+y^2 <= 1

%n= 100;

count = 0;

%tic

for i= 1:n

cond= c(i)^2 + d(i)^2;

if cond <1

count = count + 1;

plot(c(i), d(i), 'g+')

pause(0.001)

else

plot(c(i), d(i), 'bd')

end

end

%toc

disp(count)

pi1 = 4*(count/n);

%tic

rsquare = c.^2 + d.^2;

%figure, plot(rsquare)

hold off

count3= length(find(rsquare <1));

%toc