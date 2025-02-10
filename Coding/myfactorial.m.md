function[count,fact]= myfactorial(a,thresh)

% MYFACTORIAL computes product of a vector as long as the product is

% greater than a threshold

%

% [count,fact]= myfactorial(a,thresh)

%

% inputs a : vector(nx1 matrix) of numbers

% t : threshold

%

% outputs count : number of multiplications

% fact: final product above threshold

% initialize product and count

fact = 1;

count = 1;

fact = fact * a(count);

while (fact > thresh) && (count < (length(a)-1))

count = count + 1;

fact = fact * a(count);

end

if count < length(a)

fact=fact/a(count);

count = count-1;

else

fact = [];

count = [];

end