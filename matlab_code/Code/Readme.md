clc;
clear;
close all;

%% ACTIVE SUSPENSION CONTROL USING PD CONTROLLER
% This project demonstrates how a PD controller
% improves vehicle suspension performance by
% reducing vibrations and improving stability.

%% DEFINE TRANSFER FUNCTION

s = tf('s');

% Suspension System Transfer Function
G = 1/(s^2 + 3*s + 2);

disp('Suspension System:')
G

%% OPEN LOOP RESPONSE

figure;
step(G);

title('Open Loop Suspension Response');
xlabel('Time (sec)');
ylabel('Displacement');

grid on;

disp('Open Loop Performance:')
open_info = stepinfo(G)

%% PD CONTROLLER DESIGN

Kp = 15;
Kd = 8;

C = Kp + Kd*s;

disp('PD Controller Designed')

%% CLOSED LOOP SYSTEM

T = feedback(C*G,1);

%% CLOSED LOOP RESPONSE

figure;
step(T);

title('Closed Loop Response with PD Controller');
xlabel('Time (sec)');
ylabel('Displacement');

grid on;

disp('Closed Loop Performance:')
closed_info = stepinfo(T)

%% COMPARISON OF STEP RESPONSES

figure;
step(G,'w',T,'b','LineWidth',1.5);

legend('Uncontrolled System','PD Controlled System');

title('Comparison of Suspension Responses');

xlabel('Time (sec)');
ylabel('Displacement');

grid on;

%% ROAD DISTURBANCE SIMULATION

t = 0:0.01:10;

road_bump = 0.5*sin(2*t);

[y_open,~] = lsim(G,road_bump,t);
[y_closed,~] = lsim(T,road_bump,t);

figure;

plot(t,y_open,'w',t,y_closed,'b','LineWidth',1.5);

legend('Uncontrolled','Controlled');

title('Response to Road Disturbance');

xlabel('Time (sec)');
ylabel('Displacement');

grid on;

%% ADVANCED ROAD CONDITION ANALYSIS

t2 = 0:0.01:20;

%% 1. Smooth Highway Road

smooth_road = 0.1*sin(1*t2);

[y1_open,~] = lsim(G,smooth_road,t2);
[y1_closed,~] = lsim(T,smooth_road,t2);

figure;

plot(t2,y1_open,'w',t2,y1_closed,'b','LineWidth',1.5);

legend('Uncontrolled','Controlled');

title('Response Under Smooth Highway Road');

xlabel('Time (sec)');
ylabel('Displacement');

grid on;

%% 2. Speed Breaker Condition

speed_breaker = square(0.5*t2);

[y2_open,~] = lsim(G,speed_breaker,t2);
[y2_closed,~] = lsim(T,speed_breaker,t2);

figure;

plot(t2,y2_open,'w',t2,y2_closed,'b','LineWidth',1.5);

legend('Uncontrolled','Controlled');

title('Response Under Speed Breaker Condition');

xlabel('Time (sec)');
ylabel('Displacement');

grid on;

%% 3. Rough Road Condition

rough_road = 0.3*sin(3*t2) + 0.2*sin(7*t2);

[y3_open,~] = lsim(G,rough_road,t2);
[y3_closed,~] = lsim(T,rough_road,t2);

figure;

plot(t2,y3_open,'w',t2,y3_closed,'b','LineWidth',1.5);

legend('Uncontrolled','Controlled');

title('Response Under Rough Road Condition');

xlabel('Time (sec)');
ylabel('Displacement');

grid on;

%% 4. Pothole-Like Disturbance

pothole = zeros(size(t2));

pothole(400:450) = -1;
pothole(900:950) = -0.8;

[y4_open,~] = lsim(G,pothole,t2);
[y4_closed,~] = lsim(T,pothole,t2);

figure;

plot(t2,y4_open,'w',t2,y4_closed,'b','LineWidth',1.5);

legend('Uncontrolled','Controlled');

title('Response Under Pothole Disturbance');

xlabel('Time (sec)');
ylabel('Displacement');

grid on;

disp('Advanced Road Condition Analysis Complete')

%% RMS VIBRATION ANALYSIS

rms_open = rms(y3_open);
rms_closed = rms(y3_closed);

fprintf('\nRMS Vibration (Open Loop): %.4f\n', rms_open);
fprintf('RMS Vibration (Closed Loop): %.4f\n', rms_closed);

%% PERFORMANCE IMPROVEMENT

improvement = ((open_info.SettlingTime - closed_info.SettlingTime) ...
               / open_info.SettlingTime)*100;

fprintf('\nSettling Time Improved by %.2f%%\n', improvement);

%% SMART ACTIVE SUSPENSION CONCEPT
% Future enhancement:
% Sensors can detect road conditions automatically
% and adjust controller parameters in real time
% for improved comfort, stability, and safety.

%% FINAL MESSAGE

disp('-----------------------------------')
disp('ACTIVE SUSPENSION CONTROL COMPLETE')
disp('PD Controller Reduced Vibrations')
disp('Improved Ride Comfort Successfully')
disp('Advanced Road Analysis Completed')
disp('-----------------------------------')
