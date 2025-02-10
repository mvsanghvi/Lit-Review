%test generateSimplex function

clear;

close all;

clc;

X0 = [0,0];

simplexsize = 1;

[simplex]= generateSimplex_2D(X0, simplexsize);

figure;

plot([simplex(:,1);simplex(1,1)], [simplex(:,2);simplex(1,2)])