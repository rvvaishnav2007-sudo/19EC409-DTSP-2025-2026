# EXP 1 A : COMPUTATION OF DFT USING DIRECT AND FFT

# AIM: 
 To Obtain DFT and FFT of a given sequence in SCILAB. 

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM DIRECT METHOD: 
````
clc; 
clear; 
xn=[1 1 1 1 0 0 0 0]; 
 
n1=0:1:length(xn)-1; 
subplot(3,1,1); 
plot2d3(n1,xn); 
xlabel('Time n'); 
ylabel('Amplitude xn'); 
title('Input Sequence'); 
j=sqrt(-1); 
N=length(xn); 
Xk=zeros(1,N); 
for k=0:N-1 
for n=0:N-1 
Xk(k+1)=Xk(k+1)+xn(n+1)*exp((-j*2*%pi*k*n)/N); 
end  
 
end 
disp(Xk) 
K1=0:1:length(Xk)-1; 
magnitude=abs(Xk) 
subplot(3,1,2); 
plot2d3(K1,magnitude); 
xlabel('frequency(Hz)'); 
ylabel('magnitude(gain)'); 
title('magnitude spectrum'); 
angle = atan(imag(Xk),real(Xk)) 
subplot(3,1,3); 
plot2d3(K1,angle); 
xlabel('frequency(Hz)'); 
ylabel('Phase'); 
title('Phase spectrum');
````
#PROGRAM FFT:

````
 
 
clear; 
clc; 
close; 
xn = [0.5 0.5 0.5 0.5 0 0 0 0] 
 
n1=0:1:length(xn)-1; 
subplot(2,2,1); 
plot2d3(n1,xn); 
xlabel('Time n'); 
ylabel('Amplitude'); 
title('Input Sequence'); 
 
Xk = fft(xn); 
 
K1=0:1:length(Xk)-1; 
magnitude=abs(Xk) 
subplot(2,2,2); 
plot2d3(K1,magnitude); 
xlabel('frequency(Hz)'); 
ylabel('magnitude(gain)'); 
title('magnitude spectrum'); 
angle = atan(imag(Xk),real(Xk)) 
subplot(2,2,3); 
plot2d3(K1,angle); 
xlabel('frequency(Hz)'); 
ylabel('Phase'); 
title('Phase spectrum') 
y= ifft(Xk) 
 
n2=0:1:length(y)-1; 
subplot(2,2,4) 
plot2d3(n2,y) 
xlabel('Time n'); 
ylabel('Amplitude'); 
title('Inverse FFT OF X(K)'); 

````
# OUTPUT FOR DIRECT METHOD: 


<img width="775" height="729" alt="image" src="https://github.com/user-attachments/assets/2fceab39-f49d-45d9-8999-dee82a6683ba" />

# OUTPUT FOR FFT:

<img width="760" height="734" alt="image" src="https://github.com/user-attachments/assets/e77d3af5-3a6e-4564-b866-fa31f32cbead" />



# RESULT: 
COMPUTATION OF DFT USING DIRECT AND FFT METHOD ARE EXECUTED SUCCESSFULLY IN SCILAB
