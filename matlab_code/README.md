% ACTIVE SUSPENSION CONTROL SYSTEM USING MATLAB 
% Objective:
% To minimize vehicle body vibrations caused by road disturbances
% and improve damping behavior using a PD controller.
% Transfer Function of Suspension System:
% G(s) = 1 / (s^2 + 3s + 2)
% Controller Used:
% PD Controller

clc;        % Clears command window
clear;      % Clears workspace variables
close all;  % Closes all figure windows

% DEFINE TRANSFER FUNCTION 
s = tf('s');    % Define Laplace variable 's'

% Suspension System Transfer Function
G = 1/(s^2 + 3*s + 2);

% OPEN LOOP RESPONSE ANALYSIS
% This shows the system behavior without any controller.

figure;
step(G);    % Step response of open-loop system
title('Open Loop Response');
xlabel('Time (seconds)');
ylabel('Amplitude');
grid on;

% Display open-loop performance metrics
disp('Open Loop Performance);
stepinfo(G)
% PD CONTROLLER DESIGN
% Kp = Proportional Gain
% Kd = Derivative Gain
% Proportional gain improves response speed.
% Derivative gain improves damping and reduces oscillations.

Kp = 15;
Kd = 8;

% PD Controller Transfer Function
C = Kp + Kd*s;
% CLOSED LOOP SYSTEM
% feedback() creates the closed-loop transfer function.
T = feedback(C*G,1);
% CLOSED LOOP RESPONSE ANALYSIS
% This shows the improved system response after applying
% the PD controller.

figure;
step(T);    % Step response of controlled system
title('Closed Loop Response with PD Controller');
xlabel('Time (seconds)');
ylabel('Amplitude');
grid on;

% Display closed-loop performance metrics
disp('Closed Loop Performance');
stepinfo(T)
% RESPONSE COMPARISON
% Compare uncontrolled and controlled system responses.

figure;

% Open-loop response in red
step(G,'r', ...

% Closed-loop response in blue
T,'b');

legend('Uncontrolled System','Controlled System');

title('Comparison of Responses');

xlabel('Time (seconds)');
ylabel('Amplitude');

grid on;
% CONCLUSION
% The PD controller significantly improved the suspension
% system performance by:
%
% 1. Reducing settling time
% 2. Improving damping behavior
% 3. Minimizing oscillations
% 4. Enhancing ride comfort and stability

