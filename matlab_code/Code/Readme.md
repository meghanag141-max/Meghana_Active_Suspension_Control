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
% Represents vehicle body dynamics

G = 1/(s^2 + 3*s + 2);

disp('Suspension System:')
G

%% OPEN LOOP RESPONSE
% Suspension WITHOUT controller

figure;
step(G);
title('Open Loop Suspension Response');
xlabel('Time (sec)');
ylabel('Displacement');
grid on;

disp('Open Loop Performance:')
open_info = stepinfo(G)

%% PD CONTROLLER DESIGN
% P improves response speed
% D reduces oscillations

Kp = 15;
Kd = 8;

C = Kp + Kd*s;

disp('PD Controller Designed')

%% CLOSED LOOP SYSTEM
% Active suspension using feedback control

T = feedback(C*G,1);

%% CLOSED LOOP RESPONSE
% Suspension WITH PD controller

figure;
step(T);
title('Closed Loop Response with PD Controller');
xlabel('Time (sec)');
ylabel('Displacement');
grid on;

disp('Closed Loop Performance:')
closed_info = stepinfo(T)

%% COMPARISON OF RESPONSES
% Comparison between uncontrolled and controlled system

figure;
step(G,'r',T,'b');
legend('Uncontrolled System','PD Controlled System');
title('Comparison of Suspension Responses');
xlabel('Time (sec)');
ylabel('Displacement');
grid on;

%% ROAD DISTURBANCE SIMULATION
% Simulates rough road conditions

t = 0:0.01:10;

road_bump = 0.5*sin(2*t);

figure;
lsim(T,road_bump,t);
title('Response to Road Disturbance');
xlabel('Time (sec)');
ylabel('Displacement');
grid on;

%% ADVANCED ROAD CONDITION ANALYSIS
% Simulation of different real-world road conditions

t2 = 0:0.01:20;

%% 1. Smooth Highway Road

smooth_road = 0.1*sin(1*t2);

figure;
lsim(T, smooth_road, t2);

title('Response Under Smooth Highway Road');
xlabel('Time (sec)');
ylabel('Displacement');
grid on;

%% 2. Speed Breaker Condition

speed_breaker = square(0.5*t2);

figure;
lsim(T, speed_breaker, t2);

title('Response Under Speed Breaker Condition');
xlabel('Time (sec)');
ylabel('Displacement');
grid on;

%% 3. Rough Road Condition

rough_road = 0.3*sin(3*t2) + 0.2*sin(7*t2);

figure;
lsim(T, rough_road, t2);

title('Response Under Rough Road Condition');
xlabel('Time (sec)');
ylabel('Displacement');
grid on;

%% 4. Pothole-Like Disturbance

pothole = zeros(size(t2));

pothole(400:450) = -1;
pothole(900:950) = -0.8;

figure;
lsim(T, pothole, t2);

title('Response Under Pothole Disturbance');
xlabel('Time (sec)');
ylabel('Displacement');
grid on;

disp('Advanced Road Condition Analysis Complete')

%% SMART ACTIVE SUSPENSION CONCEPT
% Future enhancement:
% Sensors can detect road conditions automatically
% and adjust controller parameters in real time
% for improved comfort, stability, and safety.

%% PERFORMANCE IMPROVEMENT

improvement = ((open_info.SettlingTime - closed_info.SettlingTime) ...
               / open_info.SettlingTime)*100;

fprintf('\nSettling Time Improved by %.2f%%\n', improvement);

%% FINAL MESSAGE

disp('-----------------------------------')
disp('ACTIVE SUSPENSION CONTROL COMPLETE')
disp('PD Controller Reduced Vibrations')
disp('Improved Ride Comfort Successfully')
disp('Advanced Road Analysis Completed')
disp('-----------------------------------')
