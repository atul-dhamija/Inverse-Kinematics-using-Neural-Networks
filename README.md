# Inverse Kinematics using Neural Networks

This project is aimed to calculate the inverse kinematics of a 3-DoF robotic manipulator using neural networks. The complexity of this problem is given by the robot’s geometry and the nonlinear trigonometric equations that describe the mapping between the Cartesian space and the joint space.




## Dependencies

- Cyberobotics, Webots
- Python==3.7
- Numpy
- Tensorflow




## Approach

We have designed a deep neural network for prediciting the joint rotations of the manipulator given the position of the end effector. For training the neural networks the data was generated with the help of WeBots simulator, position of the end effector was recorded and was saved in X_train.csv file, while the joint rotations were recorded in Y_train.csv. Then the data is passed through a deep linear regression model to train it. 

### Dataset generation

In this postion of end effector is recorded(using supervisor node in WeBots) for every randomly selected theta1, theta2, theta3 in range -3.14 to +3.14 radians, theta1, theta2, theta3 were recorded in Y_train.csv and position of end effector was recorded in X_train.csv. In this collision is set off, to avoid errors as data points are taken randomly.

![Hnet com-image](https://user-images.githubusercontent.com/64823050/130271518-dd71215f-9cd3-417b-af3c-406509dc62dd.gif)

### Neural Network Architecture

The neural network contain layers as shown, with a relu activation function at intermediate layers and a linear activation function at final layer with 3 outputs.

![repo12](https://user-images.githubusercontent.com/64823050/130329974-3b6fcf90-af34-4e33-a55b-b7b0eac2dbae.png)




## Results

The trained neural network was used to predict the joint angles for end effector position x = 0.40212911, y = 1.116457, z = -0.48671574, and the result is shown in GIF.

![Hnet-image](https://user-images.githubusercontent.com/64823050/130329990-f971c5ec-b915-47a9-a528-4472f07ac505.gif)

The overall accuracy was 72.73% with a precision of 0.2.




## References

[A study of generalization ability of neural network for manipulator inverse kinematics](https://ieeexplore.ieee.org/document/239161)
