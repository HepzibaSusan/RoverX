A Kalman filter is a powerful mathematical tool used for estimating the state of a dynamic system from a series of noisy measurements. It is widely utilized in various fields such as engineering, robotics, finance, and aerospace due to its effectiveness in providing accurate and reliable estimates. Here is a brief introduction to the concept, history, and applications of Kalman filters.

#### Concept

At its core, the Kalman filter operates in a two-step process: **prediction and update.**

1. **Prediction Step:**
    
    - In this step, the current state and error covariance are used to predict the state and error covariance at the next time step. This involves applying the system's dynamic model, which describes how the state evolves over time.
    
1. **Update Step:**
    
    - Once a new measurement is available, the predicted state is updated using this measurement. This update is done in a way that minimizes the mean square error, taking into account both the uncertainty in the prediction and the uncertainty in the measurement.

The Kalman filter assumes that the process noise (uncertainty in the system model) and measurement noise (uncertainty in the measurements) are both Gaussian and that their respective covariances are known.

#### State-Space Representation

The state-space representation of a dynamic system includes the state equation (process model) and the measurement equation. 

1. **State Equation (Process Model):**
   ![[Pasted image 20240531181142.png]]
###### 2. Measurement Equation
  
![[Pasted image 20240531181334.png]]

![[Pasted image 20240531183033.png]]
![[Pasted image 20240531183059.png]]
### Algorithm Steps:

1. **Initialization**: Initialize state estimate 𝑥0​ and error covariance 𝑃0.
2. **Prediction**:
    - Predict the next state and error covariance using the state transition matrix and process noise covariance.
3. **Update**:
    - Compute the Kalman gain.
    - Update the state estimate based on the measurement.
    - Update the error covariance.
