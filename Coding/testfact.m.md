%Run myfactorial 100 times to test convergence

for i=1:100

a= rand(400,1);

[c(i), p(i)]=myfactorial(a, 10^-3);

end

plot(c);
end