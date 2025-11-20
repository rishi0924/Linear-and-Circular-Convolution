# EXP 1 : Linear and Circular Convolution

## AIM: 

 To perform Linear and Circular Convolution for two given sequence using SCILAB. 

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM (Linear Convolution): 

clc;
clear;


x = [1,1,2,1];
h = [1,2,3,4];


Lx = length(x);
Lh = length(h);
Ly = Lx + Lh - 1;


x_padded = [x, zeros(1, Lh - 1)];
h_padded = [h, zeros(1, Lx - 1)];


y = zeros(1, Ly);
for n = 1:Ly
    for k = 1:n
        if (k <= Lx & (n - k + 1) <= Lh) then
            y(n) = y(n) + x(k) * h(n - k + 1);
        end
    end
end

disp("Linear Convolution Result:");
disp(y);
## PROGRAM (Circular Convolution): 
clc;
clear;

x = [1, 2, 2,1];
h = [1, 2,3,1];


N = max(length(x), length(h));


x = [x, zeros(1, N - length(x))];
h = [h, zeros(1, N - length(h))];


y = zeros(1, N);


for n = 1:N
    for k = 1:N
        index = modulo(n - k + N, N) + 1;
        y(n) = y(n) + x(k) * h(index);
    end
end

disp("Circular Convolution Result:");
disp(y);

## OUTPUT (Linear Convolution): 
<img width="1676" height="392" alt="Screenshot 2025-09-01 025542" src="https://github.com/user-attachments/assets/985b47aa-a923-4852-aa9b-9073da387558" />

## OUTPUT (Circular Convolution): 
<img width="1678" height="424" alt="Screenshot 2025-09-01 025615" src="https://github.com/user-attachments/assets/200f5888-c5f5-4a49-9002-0627570f601e" />

## RESULT: 
Linear and Circular Convolution for two given sequence is obtained using SCILAB
