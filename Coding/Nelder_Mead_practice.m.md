clear all

clc

close all

%Assignment 1:

%use a 'surf' to visualize this function,

% 𝑓(𝑥, 𝑦) = (𝑥 − 𝑎)2 + (𝑦 − 𝑏)2

%define an equation

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

%make a surface

figure;

surf(A,B,z)

xlabel('A')

ylabel('B')

zlabel('Loss function')

%make a contour

figure;

contour(A,B,z)

xlabel('A')

ylabel('B')

%set a = 1 & b = 3

%a = 1;

%b = 3;

%Where is the minimum of this function happening?

%Choose different values for a and b. What does it change?

%Assignment 2: