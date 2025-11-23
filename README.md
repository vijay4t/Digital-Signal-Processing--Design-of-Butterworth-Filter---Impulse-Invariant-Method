# Digital-Signal-Processing--Design-of-Butterworth-Filter---Impulse-Invariant-Method
## AIM:
To design of 2nd order Low Pass Butterworth Filter using using Impulse Invariant Transformation 
## SOFTWARE REQUIRED: 
MAT LAB R2012
## ALGORITHM:
Step 1: Open MAT LAB. Write the program. 

Step 2: Read the values of Ap,As,Pass band frequency,Stop band frequency.

Step 3: Initialise some conditions find out the order (N) value.

Step 4: Find out the transfer function of the filter and magnitude of that filter. 

Step 5: Plot the magnitude spectrum with x-label and y-label with suitable title. 

Step 6: Terminate the program.

## PROGRAM:
```
clc 
clear all 
close all 
Ap=input('enter the value of Ap'); 
As=input('enter the value of As'); 
wp=input('enter the PB frequency'); 
ws=input('enter the SB frequency'); 
T=input('enter the value of time'); 
omega_p=(wp/T) 
omega_s=(ws/T) 
alpha_p=20*log10(Ap) 
alpha_s=20*log10(As) 
[N wc]=buttord(omega_p,omega_s,alpha_p,alpha_s,'s') 
[num den]=butter(N,1,'s') 
display('normalised transfer function'); 
hs=tf(num,den) 
[num1 den1]=butter(N,wc,'s') 
display('unnormalised transfer function'); 
hs1=tf(num1,den1) 
[numz denz]=impinvar(num1,den1,1/T) 
hz=tf(numz,denz,T) 
display('digital transfer function'); 
w=0:pi/16:pi 
y=freqz(numz,denz,w);
%MAGNITUDE SPECTRUM 
y1=abs(y); 
plot(w,y1); 
xlabel('frequency'); 
ylabel('magnitude'); 
title('magnitude response butterworth LPF');
```

## OUTPUT:
<img width="684" height="621" alt="Screenshot 2025-11-17 180736" src="https://github.com/user-attachments/assets/ddcbf59b-dcf6-45f9-b0a0-172c9e64bcd2" />

## RESULT:
![7](https://github.com/user-attachments/assets/e99fc13f-5bee-44bf-887b-53414681da2d)




## RESULT:
