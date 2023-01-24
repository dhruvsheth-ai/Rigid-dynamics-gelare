# Rigid-dynamics-gelare
Repository for exploring simulations and rigid dynamical systems to model constraints in Gelare. 

The work in this repository was inspired by https://github.com/alx87grd/AlexRobotics and here, I explore modelling a simple pendulum and a constrained pendulum setup using Phase Plane analysis. The main aim is to apply Phase Plane visualization to analyze constraints in a 4 DOF Robotic Arm spatially. Since phase planes are especially useful for modelling non-linear system, the motion of a constrained robotic arm would be analyzed clearly.

**Phase Plane Analysis for a simple pendulum system without constraints**:
<h3> $ml^2 \ddot{q} + b \dot{q}  + m g l \sin q = \tau$ </h3>
The following equation is the dynamic equation consisting of mass with some linear damping $b$ and an external force input $f$. The state vector here is defined as:

<h3> $x = \begin{bmatrix} q \\ \dot{q} \end{bmatrix}$ </h3>

![image](https://user-images.githubusercontent.com/67831664/214374453-71a46e2c-d0d8-4d8a-afc5-57092445dde8.png)

![image](https://user-images.githubusercontent.com/67831664/214374478-37a6350b-bcc0-44a4-89fb-d513e7206d48.png)


With some initial velocity, the pendulum osscilates about the mean position:

![image](https://user-images.githubusercontent.com/67831664/214374680-5613bae8-7c4a-4497-91a2-a7d13e55e84a.png)

When damping is introduced in the dynamic equation, the phase plane dynamically changes to:

![image](https://user-images.githubusercontent.com/67831664/214374806-623ae595-a148-40fa-bf55-36fa5f32efc4.png)

Damping in actual environment:
https://user-images.githubusercontent.com/67831664/214375054-9368c5fa-d204-4212-905e-720dfda4abc2.mp4

The example given below is for a custom open-loop feedback controlled Custom Dynamic System in the phase plane. The example can be reproduced through the Jupyter Notebook in the repository:

$\dot{x} = f(x,u,t)$

where $x$ is the state vector, $u$ is an input vector and $t$ is time.

$\dot{x} = f(x,u)$

$u = c(x)$

$\dot{x} = f(x,u) = f(x, c(x))  = f_{cl}(x)$

$f_{cl}$ is the "Closed-loop" dynamic. 

$u = K ( r - y )$

where $K$ is a $1 \times 2 $ matrix of gains, $u$ is the force input that the controller will apply, $r$ is the reference (a desired state vector) and $y$ is the actual measured state vector.

![image](https://user-images.githubusercontent.com/67831664/214375528-71e92051-5007-4783-b199-56e20f2d7de1.png)
