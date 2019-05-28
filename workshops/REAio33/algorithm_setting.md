# Hyperparameters

Hyperparameters are variables to control your reinforcement learning training. They can be tuned to optimize the training time and your model performance.

> Feel free to leave them unchanged. However, consider changing them as you start iterating on your models as they can significantly improve training convergence.

Before we dive in, let's just call out some terms we will be using to ensure you are familiar with what they mean.

A **step**, also known as experience, is a tuple of (s,a,r,s’), where s stands for an observation (or state) captured by the camera, a for an action taken by the vehicle, r for the expected reward incurred by the said action, and s’ for the new observation (or new state) after the action is taken.

An **episode** is a period in which the vehicle starts from a given starting point and ends up completing the track or going off the track. Thus an episode is a sequence of steps, or experience. Different episodes can have different lengths.

An **experience buffer** consists of a number of ordered steps collected over fixed number of episodes of varying lengths during training. It serves as the source from which input is drawn for updating the underlying (policy and value) neural networks.

A **batch** is an ordered list of experiences, representing a portion of the experience obtained in the simulation over a period of time, and it is used to update the policy network weights.

A set of batches sampled at random from an experience buffer is called a **training data set**, and used for training the policy network weights.

## Gradient descent batch size

Determine how many images will be used for training. How many training data to loop through before training the model.

The number of recent vehicle experiences sampled at random from an experience buffer and used for updating the underlying deep-learning neural network weights. Random sampling helps reduce correlations inherent in the input data. Use a larger batch size to promote more stable and smooth updates to the neural network weights, but be aware of the possibility that the training may be longer or slower.

The batch is a subset of an experience buffer that is composed of images captured by the camera mounted on the AWS DeepRacer vehicle and actions taken by the vehicle.

## Number of epochs

How many times the algorithm will pass through the batch data set before updating the training weights.

The number of passes through the training data to update the neural network weights during gradient descent. The training data corresponds to random samples from the experience buffer. Use a larger number of epochs to promote more stable updates, but expect a slower training. When the batch size is small, you can use a smaller number of epochs.

- You want to increase the number of epochs until the validation accuracy is minimized.
- Larger number of epochs is acceptable when the batch size is large

## Learning rate

Controls the speed at which your algorithm learns

During each update, a portion of the new weight can be from the gradient-descent (or ascent) contribution and the rest from the existing weight value. The learning rate controls how much a gradient-descent (or ascent) update contributes to the network weights. Use a higher learning rate to include more gradient-descent contributions for faster training, but be aware of the possibility that the expected reward may not converge if the learning rate is too large.

## Entropy

The degree of uncertainty used to determine when to add randomness to the policy distribution. The added uncertainty helps the AWS DeepRacer vehicle explore the action space more broadly. A larger entropy value encourages the vehicle to explore the action space more thoroughly.

## Discount factor

The discount factor determines how much of future rewards are discounted in calculating the reward at a given state as the averaged reward over all the future states. The discount factor of 0 means the current state is independent of future steps, whereas the discount factor 1 means that contributions from all of the future steps are included. With the discount factor of 0.9, the expected reward at a given step includes rewards from an order of 10 future steps. With the discount factor of 0.999, the expected reward includes rewards from an order of 1000 future steps.

## Loss type

The type of the objective function to update the network weights. A good training algorithm should make incremental changes to the vehicle’s strategy so that it gradually transitions from taking random actions to taking strategic actions to increase reward. But if it makes too big a change then the training becomes unstable and the agent ends up not learning. The Huber and Mean squared error loss types behave similarly for small updates. But as the updates become larger, the Huber loss takes smaller increments compared to the Mean squared error loss. When you have convergence problems, use the Huber loss type. When convergence is good and you want to train faster, use the Mean squared error loss type.

## Number of experience episodes between each policy-updating iteration

The size of the experience buffer used to draw training data from for learning policy network weights. An episode is a period in which the vehicle starts from a given starting point and ends up completing the track or going off the track. Different episodes can have different lengths. For simple reinforcement-learning problems, a small experience buffer may be sufficient and learning will be fast. For more complex problems which have more local maxima, a larger experience buffer is necessary to provide more uncorrelated data points. In this case, training will be slower but more stable. The recommended values are 10, 20 and 40.
