# Optimization
Optimization

Reference  Chih Yu Hsu https://github.com/tccnchsu/Numerical_Analysis

利用遗传算法求 y = exp(-2*(x-1)^2)  ,其中x < 2时的最大值
调用：
X = ga(@myfit,1,1,2)
y = exp(-2*(X-1)^2)

其中：
function f = myfit(x)
    f = exp(-2*(x-1)^2);
    f = -f;
end



Chaper 1   Solve the problem of Extremum of multivariate function

Tips : 在处理王小鹏学长那个公式时，仍然有点问题，我也不知道问题出在哪里。不过我试过了其他的多元函数求极值问题，例如简单的x1^2 + x2^2 + x3^2，就可以求解。所以不知道如何解决，或许是我对公式理解太少？ 此外，需要对求解的三个未知变量设置初值，就在这句中“[X fval]= fmincon('x(1)^2 + x(2)^2 + x(3)^2',[1 1 1 ],[],[],[],[],[],[],'myfunc');” ， 里面的【1 1  1】 就是随便设定的初值。

main code：

clear all;
close all;
warning off all;

d=2;
 sigma2 = [5 .3; .3 1];
mu = [3, 4]';
  mu1 = [-5,3]';
   mu2 = [10,1]';
b = @mycon;
[X fval]= fmincon('x(1)^2 + x(2)^2 + x(3)^2',[1 1 1 ],[],[],[],[],[],[],'myfunc');
x = X(1)
y = X(2)
z = X(3)
fval

function code ：

function [ce ceq] = myfunc(x)
ce =[];
ceq = x(1)^2 + x(2)^2 + x(3)^2 - 1;
return
