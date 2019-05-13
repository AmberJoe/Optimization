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
