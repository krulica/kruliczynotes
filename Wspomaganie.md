### Wektory

```
clc
a=[1 2 3]
b=[1,2,3]
c=[1;2;4]
y=b'
c==y
c(1)=5
c==y
d=[-1.3*sin(sqrt(5)) (log(6)-5)]
e=[1:10];
e=[1:.1:10];
```
###Statg
```
function [mean,stdev,minx] = statg

global x

n = length(x);
mean = sum(x)/n;
stdev = sqrt(sum((x-mean).^2/n));

minx=x(1);
for i=2:n
    if x(i)<minx
        minx=x(i)
end
end
```
```
clc
format compact

global x

x=round(rand(1,10)*100)
mean(x)
[a,b,c]=statg
min(x)
max(x)
```
###Całka

```
format long
format compact
clc
F=@(x) 1./(x.^3-2*x-5);
F=@(x) x.^x;
F=@(x) exp(sin(x));

tol=10^(-15)

Q= quadl (F,0,pi/2,tol)
Q= quad(F,0,pi/2,tol)


h=pi/10000000;
x=0:h:pi/2;
y=exp(sin(x));

calk=y(1)/2;
for i=2:length(x)-1;
       calk=calk+y(i);
end
calk=(calk+y(end)/2)*h
```
###Interpolacja

```
clc
format compact
x=95:10:205
x1=95:0.1:205;
y=[85,76,114,143,164,281,306,358,437,470,690,702]
plot(x,y,'o')
A=[x',ones(12,1)]
yb=y'
z=A\yb
A*z-yb;
%y1=z(1)*x1.^2+z(2)*x1+z(3)
w=polyfit(x,y,1)
%y1=polyval(w,x1)
plot(x,y,'o',x1,y1)
```

###Plotowanie
```
clc
format compact
x=95:10:205
x1=95:0.1:205;
y=[85,76,114,143,164,281,306,358,437,470,690,702]
plot(x,y,'o')
A=[x',ones(12,1)]
yb=y'
z=A\yb
A*z-yb;
%y1=z(1)*x1.^2+z(2)*x1+z(3)
w=polyfit(x,y,1)
%y1=polyval(w,x1)
plot(x,y,'o',x1,y1)
```
###Funkcje Bessela

```
clc
format compact
x=0:0.2:12;
y1=Besselj(1,x);
y2=Besselj(2,x);
y3=Besselj(3,x);

figure(1)
subplot(2,2,1)

h=plot(x,y1,x,y2,x,y3);

set(h,'LineWidth',2,{'LineStyle'},{'--';':';'-.'})
set(h,{'Color'},{'r';'g';'b'})

axis ([0 12 -0.5 1])
grid on

xlabel ('Czas'); ylabel ('Amplituda')
legend(h,'1','2','3')
title ('Funkcje Bessela')
[y,ix]=min(y1);
text(x(ix),y,'Minimum\rightarrow','HorizontalAlignment','right')
```
