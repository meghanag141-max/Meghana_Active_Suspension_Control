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

%% PERFORMANCE IMPROVEMENT

improvement = ((open_info.SettlingTime - closed_info.SettlingTime) ...
               / open_info.SettlingTime)*100;

fprintf('\nSettling Time Improved by %.2f%%\n', improvement);

%% FINAL MESSAGE

disp('-----------------------------------')
disp('ACTIVE SUSPENSION CONTROL COMPLETE')
disp('PD Controller Reduced Vibrations')
disp('Improved Ride Comfort Successfully')
disp('-----------------------------------')


