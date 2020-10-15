# PID Controller



**PID controller** consists of three terms, namely proportional, integral and derivative control. The combined operation of these three controllers gives control strategy for process control  

- The proportional term domain define the steer angle at most time, for larger cte(cross track error), the steer value should be larger, this term works very well in this project.
- the integral term is used to justify system bias, it can solve the system bias caused by car or by constant curvity of road. But it may not work very well on road with unregular curvity. 
- The derivative term is used mainly to reduce the impact of proportional term and avoid overshooting with large steer angle. Then the car can move more smoothly. This term is also useful in the project.

###  Tune the parameters

I'm not familiar with interacting with simulator, so I just tune the data manually.

  *    Kp: It is valid to choice steer 1 or -1 when car at the edge of road(cte = 5), which means Kp > 1/5 may be valid, so I choose Kp =1.
  *   Kd: The d_err should be smaller than p_error at most time. It depends on the speed, and driving angle,  if the speed and driving angle are large, Kd should be a relatively small value.  I didn't try much and just found that Kd = 1 work. The Ki should be very small, 
  *   Ki: Because the integrate of the cte maybe large. I found that Ki <= 0.01 is proper(corresponding to throttle = 0.15). For the throttle, 
  *   For the throttle, my program can't work with throttle = 0.3(0.2 is ok). It is obviously that the smaller throttle is safe, so I just pick 0.15.
