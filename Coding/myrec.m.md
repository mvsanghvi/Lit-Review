% step 0: clear all existing values in memory

clear all

% step 1: define sidelength a and b

a = [17,4,67];

b= [3,5,0];

% go over all rectangles

for i = 1:length(a)

% step 2: compute area

area(i) = a(i)*b(i);

% step 3: compute perimeter

per(i)= 2*a(i)+2*b(i);

% step 4: compute angle

ang(i) = atan(b(i)/a(i));

end