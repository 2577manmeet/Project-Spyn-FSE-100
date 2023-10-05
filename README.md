# Project-Spyn-FSE-100
% gyro declaration and calibration
brick.GyroCalibrate(4);
angle = brick.GyroAngle(SensorPort);
display(angle);

% driving 
brick.ResetMotorAngle('A'); 

brick.MoveMotorAngleAbs('A', 20, 90, 'Brake'); 

brick.WaitForMotor('A'); % Wait for motor to complete motion

position = brick.GetMotorAngle('A'); % Get Current Position

display(position);

% color sensor
brick.SetColorMode(1, 2);
color = brick.ColorCode(SensorPort);
display(color);

distance = brick.UltrasonicDist(2);

% determines the end of the program
brick.beep();
brick.beep();
brick.beep();
% gets battery level
L = brick.GetBattLevel();
display(L);
v = brick.GetBattVoltage();
display(v);
