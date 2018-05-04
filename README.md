# CarND-Controls-MPC
Self-Driving Car Engineer Nanodegree Program

---

## MPC Controll


**MPC** -> Model Predictive Control

MPC is an advanced method of process control that is used to control a process while satisfying a set of constraints.


**Model Implementation :**

  **Goal :**

  The goal of Model Predictive Control is to optimize the control inputs: [δ,a]. An optimizer will tune these inputs until a low cost  vector of control inputs is found.



  **State Vector** :

  x, y : Car's position.

  psi : Car's heading direction.

  v : Car's velocity
  cte : Cross-track error.

  epsi : Orientation error


  **Latency Handling :**

  There was a latency of 100 ms introduced , to handle this , the actual data were shifted 100 ms before passing it to the MPC module "state vector " to help reduce the effect of the latency.

  **Equations :**

  <img src="img/equations.png">


  MPC attempts to approximate a continuous reference trajectory by means of discrete paths between actuations. Larger values of dt result in less frequent actuations, which makes it harder to accurately approximate a continuous reference trajectory. This is sometimes called "discretization error".


  N, dt, and T are hyperparameters you will need to tune for each model predictive controller.

  dt is set to small value because it define the time between each step , so it need to predict accurate.

  Larger  N will cause the simulator to run slower .

  At the end duration of trajectory T is defined by the dt and N.

  ***Note*** : The cost function parameters were tuned by try-and-error .
