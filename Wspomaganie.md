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
