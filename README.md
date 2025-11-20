# EXP 2 : Linear and Circular Convolution

## AIM: 

 To perform Linear and Circular Convolution for two given sequence using SCILAB. 

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM (Linear Convolution): 

// Linear Convolution

clc;

clear;

close;

x = input("Enter x(n) as a vector, e.g., [1 2 0 2]: ");

h = input("Enter h(n) as a vector, e.g., [0 1]: ");

y = conv(x, h);

disp(y, "Linear Convolution y(n) = ")

subplot(3,1,1);

plot2d3(0:length(x)-1, x);

title("x(n)");

xlabel("n");

ylabel("Amplitude");

subplot(3,1,2);

plot2d3(0:length(h)-1, h);

title("h(n)");

xlabel("n");

ylabel("Amplitude");

subplot(3,1,3);

plot2d3(0:length(y)-1, y);

title("y(n) = x(n) * h(n)");

xlabel("n");

ylabel("Amplitude");

## PROGRAM (Circular Convolution): 

// Circular Convolution

clc;

clear;

close;

x = input("Enter x(n) as a vector, e.g., [1 2 3 4]: ");

h = input("Enter h(n) as a vector, e.g., [1 2 3 4]: ");

N = length(x);

if length(h) < N then

    h = [h, zeros(1, N - length(h))];
    
elseif length(h) > N then

    x = [x, zeros(1, length(h) - N)];
    
    N = length(h);
    
end

X = fft(x, -1);

H = fft(h, -1);

Y = X .* H;

y = fft(Y, 1);  

disp(real(y), "Circular Convolution y(n) = ");

subplot(3,1,1);

plot2d3(0:N-1, x);

title("Input Sequence x[n]");

xlabel("n");

ylabel("Amplitude");

subplot(3,1,2);

plot2d3(0:N-1, h);

title("Input Sequence h[n]");

xlabel("n");

ylabel("Amplitude");

subplot(3,1,3);

plot2d3(0:N-1, real(y));

title("Circular Convolution y[n]");

xlabel("n");

ylabel("Amplitude");

## OUTPUT (Linear Convolution): 

![WhatsApp Image 2025-11-20 at 18 27 48_359a75f9](https://github.com/user-attachments/assets/53eec115-d711-4d94-b7fe-c691bed9c118)


## OUTPUT (Circular Convolution): 

![WhatsApp Image 2025-11-20 at 18 28 09_1486974e](https://github.com/user-attachments/assets/5e4d1084-95de-45fd-ae5c-93073d847d8b)


## RESULT: 

Thus, the linear convolution and circular convolution of the two given sequences were performed and its result was verified.
