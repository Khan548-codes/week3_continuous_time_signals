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

# Discription
1. Unit Impulse Signal
The unit impulse, also called the delta function, is a signal that is zero everywhere except at the origin, where it has an infinitely high value. It is not a practical signal but is used in theory because it can model an ideal “instantaneous pulse.” In MATLAB, we approximate it by plotting a spike at t=0.

2. Unit Step Signal
The unit step signal stays at zero for all negative time and becomes one at time zero and after. It acts like a switch that turns a system “on” at t=0.

3. Unit Ramp Signal
The unit ramp signal starts from zero at t=0 and increases linearly with time. For negative time, it remains zero. It represents a steadily increasing input, like a line with positive slope starting at the origin.

4. Exponential Signal
The exponential signal changes rapidly depending on its exponent. If the exponent is negative, the signal decays toward zero as time increases. If it is positive, the signal grows rapidly. Exponential signals are very common in natural and engineering systems, such as charging and discharging in circuits.

5. Signum (Sign) Signal
The signum signal shows only the sign of time. It has the value −1 for negative time, 0 at time zero, and +1 for positive time. It is often used to describe symmetry in signals.

6. Sinc Signal
The sinc signal has a central peak at the origin and then oscillates on both sides with decreasing amplitude. It is very important in signal processing and communications, especially in the theory of sampling, where it is used to reconstruct signals.

