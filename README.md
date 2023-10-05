# Project-Spyn-FSE-100
% gyro declaration and calibration
brick.GyroCalibrate(4);
angle = brick.GyroAngle(SensorPort);
display(angle);

% driving 
brick.ResetMotorAngle('A'); 
brick.ResetMotorAngle('B'); 

brick.MoveMotorAngleAbs('A', 100, 90, 'Brake');
brick.MoveMotorAngleAbs('B', 100, 90, 'Brake');

% brick.WaitForMotor('A'); % Wait for motor to complete motion

position = brick.GetMotorAngle('A'); % Get Current Position

display(position);

% color sensor
brick.SetColorMode(2, 2);
color = brick.ColorCode(2);
display(color);

% measures distance
distance = brick.UltrasonicDist(3);

% determines the end of the program
brick.beep();
brick.beep();
brick.beep();
% gets battery level
L = brick.GetBattLevel();
display(L);
v = brick.GetBattVoltage();
display(v);
