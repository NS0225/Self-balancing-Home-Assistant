# Self-balancing-Robot
#Introduction
A 2 wheeler self-balancing robot is introduced in this project. Main aim of this project is to decrease the cost and execute an innovative idea.

#Equipments Used
Arduino Uno
Gyro-accelerometer(MPU-6050)
Motor Driver Module(L293D)
2 high-torque motors(>150rpm)

#Working
It is mainly based on PID controller mechanism. If the bot gets tilted, it automatically observes a torque in the opposite direction and this makes it to stay in quillibrium position. 
A set-point is set innitially. Gyro-accelerometer measures the present position of its axis. The difference of this position from set-point becomes the error(e(t)) at that instance. Main objective is to minimise e(t).

According to PID equation:
o(t)=kp*e(t) + ki*integral(e(t)) + kd*d/dt(e(t))
  where o(t) = output of PID controller
        kp, ki, kd are proportional, integral, and derivative constants respectively

Values of kp, ki, kd are experimental(depends on several features like the weight of the bot, speed of motor etc.).
The output is fed to PWM pins of Arduino which controls the speed variation of motors via Motor Driver Module.

For manual movement of the bot, the set-point is manually given by the user using HC-05. To achieve the new set-point the bot moves forward and backward.
