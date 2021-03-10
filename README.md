# MATLAB-code-for-Voltage-Regulation-and-Efficiency-Of-transmission-line-with-Recieving-End-parameters



MATLAB code for Voltage Regulation and Efficiency Of transmission line with Recieving End parameters given


Aim:-To write computer program and obtain voltage regulation and efficiency of short transmission line for different specified set of receiving end quantities (different load at leading, unity and lagging power factor).

Questions:-

A single phase 50 Hz generator supplies an inductive load of 5000 kW at a power factor of 0.707 lagging by means of an overhead transmission line 20 km long. The line resistance and inductance are 0.0195 ohms and 0.63 mH per km. The voltage at the receiving-end required to be kept constant at 10 kV.

Find :-

1. Sending -end voltage,

2. voltage regulation at leading, lagging and unity power factor,

3. Transmission efficiency

Matlab Code:-

%Find voltage at sending end, percentage regulation and transmission efficiency

clc;

clear all;

P=5000; %kW power

Vr=10000; %kVrecieving voltage

pf=input(‘Enter the value of power factor : ‘); %for lagging power factor

mop=input(‘lead=1,lag= -1,unity=0\n’);

csd= asind(pf);

R=0.39; %ohm resistance

X=3.96; %ohm inductance

I=P*1000/(Vr*pf);

c=(Vr);

b=(I*X*sind(csd))+I*R*cosd(csd);

if mop== 1

fprintf(‘\n Power factor is leading’)

Vs=c-b;

Pr=((Vs-Vr)*100)/Vr;

fprintf(‘\n Voltage at sending end(Vs)= %.3fV\n’,Vs) ;

elseif mop== -1

fprintf(‘\n power factor is lagging’)

Vs=c+b;

Pr=((Vs-Vr)*100)/Vr;

fprintf(‘\n Voltage at sending end(Vs)= %.3fV\n’,Vs) ;

elseif mop== 0 && pf == 1

fprintf(‘\n power factor is unity’)

Vs=c+(I*R*cosd(csd))

Pr=((Vs-Vr)*100)/Vr;

fprintf(‘Voltage at sending end(Vs)= %.3fV\n’,Vs) ;

end

if Pr < 0

Pr=(-Pr);

end

fprintf(‘\n Percentage regulation= %f percent’,Pr);

Lineloss =I*I*R/1000; % line losses

efficiency=P*100/(P+Lineloss);

fprintf(‘\n Transmission efficiency= %.2f percent’, efficiency)

Output:-

For leading:-

Enter the value of power factor : 0.707

lead=1,lag= -1,unity=0

1

Power factor is leading

Voltage at sending end(Vs)= 7824.941V

Percentage regulation= 21.750589 percent

Transmission efficiency= 96.25 percent

For lagging:-

Enter the value of power factor : 0.707

lead=1,lag= -1,unity=0

-1

power factor is lagging

Voltage at sending end(Vs)= 12175.059V

Percentage regulation= 21.750589 percent

Transmission efficiency= 96.25 percent

For unity:-

Enter the value of power factor : 1

lead=1,lag= -1,unity=0

0

power factor is unity

Vs =

10000

Voltage at sending end(Vs)= 10000.000V

Percentage regulation= 0.000000 percent

Transmission efficiency= 98.09 percent

#Written ,Coded and posted by

#Dharmik Desai,Niranjan Yadav ,Sadhu Ruchi

www.strikings.email

