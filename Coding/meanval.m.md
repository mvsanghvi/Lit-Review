clear

close

clc

%set 0: set variables

t= 0.5

count = 0

nTests = 100

%step 1: run through numbers 100 times

for i=1:nTests

a = rand;

if a>t

count=count+1

end

end

count/nTests

%step 2: generate a random value

% step 3: count if value is greater or less than 0.5