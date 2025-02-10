close all

clear all

clc

%Assignment 2:

%Task1: choose an initial guess for the function.

%- visualize the following function using %fcontourt.

%(𝑥𝑥, 𝑦𝑦) = (𝑥𝑥 − 1 )2 + (𝑦𝑦 − 3)2

x=2;

y=3;

func = @(a,b) (x-a).^2 + (y-b).^2;

%define range of paramters space (a.b)

Arange = [-10, 10];

Brange = [-10, 10];

%make mesh to create surf or contour

[A,B]= meshgrid(Arange(1):Arange(2), Brange(1):Brange(2));

%calculate loss of function value in paramter space

z= func(A,B);

%make a contour

figure;

contour(A,B,z)

hold on

a0=0;

b0=0;

dSize = 1;

%- choose an initial guess for the parameters, P = (x0, y0). During the optimization, this initial guess will converge to minimum (or maximum) point of the given function. For example, choose P = (0,0).

simplex = nan(3,2);

simplex(1,:) = [a0,b0];

simplex(2,:) = [a0-dSize,b0];

simplex(3,:) = [a0,b0-dSize];

%- Plot P on the same figure (on top of contour).

plot([simplex(:,1);simplex(1,1)], [simplex(:,2);simplex(1,2)])

hold off

%Task 2: generate the initial simplex

%In this exercise, we will write a function to generate a simplex.

%- In the Nelder-Mead algorithm, initializing a simplex around our initial guess is crucial. In 2D, a simplex is represented as a triangle, requiring three ver�ces (P1, P2, P3), each with x, y coordinates. Here is a typical approach,

%o P1 represents the initial guess, (x0, y0)

%o P2 is created based on P1 but slightly different in x-direction. So P2 = (x0 + 0.05, y0). Ofnote, 0.05 is arbitrary. It is the length of the triangle side! (One parameter for Nelder-Mead algorithm!)

%o P3 is similarly created but in the y-direction, P3 = (x0, y0+0.05).

%- Write a function to generate a simplex for the initial guess.

%- Plot the simplex on top of contour plot.

%Task 3 (optional): Choose a random number for initial guess and generate simplex