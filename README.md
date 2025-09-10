# week3_continuous_time_signals
% Continuous-Time Signal Generation
clc; clear; close all;

% Time axis (approximate continuous time with fine steps)
t = -5:0.01:5;

%% 1. Unit Impulse (delta function approximation)
% Since ideal delta is not realizable, approximate using a very narrow pulse
delta = t==0;  

figure;
stem(t, delta, 'r', 'LineWidth', 1.5); grid on;
title('Unit Impulse \delta(t)');
xlabel('t'); ylabel('\delta(t)');

%% 2. Unit Step
u = double(t >= 0);

figure;
plot(t, u, 'b', 'LineWidth', 1.5); grid on;
title('Unit Step u(t)');
xlabel('t'); ylabel('u(t)');

%% 3. Unit Ramp
r = t .* (t >= 0);

figure;
plot(t, r, 'm', 'LineWidth', 1.5); grid on;
title('Unit Ramp r(t)');
xlabel('t'); ylabel('r(t)');

%% 4. Exponential Signal
a = -0.5; % decay constant (change for growth/decay)
x_exp = exp(a*t) .* (t >= 0); % causal exponential

figure;
plot(t, x_exp, 'g', 'LineWidth', 1.5); grid on;
title('Exponential Signal e^{at}u(t)');
xlabel('t'); ylabel('x(t)');

%% 5. Signum Signal
sgn = sign(t);

figure;
plot(t, sgn, 'k', 'LineWidth', 1.5); grid on;
title('Signum Signal sgn(t)');
xlabel('t'); ylabel('sgn(t)');

%% 6. Sinc Signal
x_sinc = sinc(t); % MATLAB defines sinc(x) = sin(pi*x)/(pi*x)

figure;
plot(t, x_sinc, 'c', 'LineWidth', 1.5); grid on;
title('Sinc Signal sinc(t) = sin(\pit)/(\pit)');
xlabel('t'); ylabel('sinc(t)');

![image](/images/ss1.png)
![image](/images/ss2.png)
![image](/images/ss3.png)
![image](/images/ss4.png)
![image](/images/ss5.png)
![image](/images/ss6.png)

