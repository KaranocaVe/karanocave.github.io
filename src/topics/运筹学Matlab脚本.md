# 运筹学Matlab脚本

下面的东西可以帮你快速检查你算对了吗

## 单纯性法(min)
```C
c = [5;0;b1]  % 目标函数的系数

% 约束条件矩阵和矢量
A = [-1 1 -6;-1  -1  -2] % 转换为小于等于形式
b = [-1,-2]             % 转换为小于等于形式

% 变量下界 (没有上界，所以默认是Inf)
lb = [0;0;0]

% 使用linprog求解
options = optimoptions('linprog', 'Algorithm', 'dual-simplex');
[x, fval, exitflag, output] = linprog(c, A, b, [], [], lb, [], options);

% 输出结果
disp('解决方案 x:');
disp(x);
disp('目标函数的最小值:');
disp(fval);
```