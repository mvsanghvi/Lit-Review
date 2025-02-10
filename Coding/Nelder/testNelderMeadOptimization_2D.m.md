clear all

close all

clc

% Define the objective function

a0 = -1;

b0 = 1;

func = @(a,b) (a- a0).^2 + (b - b0).^2;

%

% figure;

% zhandle = fcontour(func, [-10 10 -10 10]);

% % set(gcf,'Position',[10 10 1000 2000])

% hold on

%

% % Initial guess

x0 = [-1 2];

% plot(x0(1),x0(2),'*')

% Tolerance and maximum number of iterations

tol = 2e-15;

max_iter = 3000;

% Run the Nelder-Mead algorithm

[xmin, fmin, iterations ] = NelderMeadOptimization2D(func, x0, tol, max_iter,1);

% Display results

fprintf('Minimum point: %s\n', num2str(xmin));

fprintf('Minimum value: %f\n', fmin);

fprintf('Iterations: %d\n', iterations);