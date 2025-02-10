% test generatesimpleX function

clear all

close all

clc

X0 = [0 , 0];

simpleXSize = 1;

[simpleX] = generatesimpleX_2D(X0,simpleXSize)

figure;

% draw the simpleX

plot([simpleX(:,1) ; simpleX(1,1)], [simpleX(:,2) ; simpleX(1,2)])

%%

[simpleX] = generateSimpleX(X0,simpleXSize)