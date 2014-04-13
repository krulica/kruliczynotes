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
