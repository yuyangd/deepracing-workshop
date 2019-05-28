# Under the hood in DeepRacer

Let's take the time to understand reinforcement learning—a powerful and growing machine learning technique that literally drives AWS DeepRacer.

With reinforcement learning, models learn by a continuous process of receiving rewards and punishments for every action taken. It’s all about rewarding positive actions and punishing negative ones. 

## RL use cases outside of AWS DeepRacer

RL has some interesting applications beyond AWS DeepRacer. Some fun applications come from the gaming world, where you can teach an agent to play games--anything from chess and Go to more advanced games like Starcraft. In these examples, the agent improves its performance by playing thousands of games against different versions of itself or other users. The agent constantly experiments with different strategies and maneuvers until it can beat its opponent.

There are some scientific applications of deep RL, as well. In some cases, it’s used to [optimize chemical reactions](https://pubs.acs.org/doi/full/10.1021/acscentsci.7b00492) for pharmaceutical companies to increase the efficiency of the process. Deep RL models do this by analyzing reaction results and choosing new experimental conditions to increase efficiency and reduce waste.

You can [use RL in portfolio management](https://github.com/awslabs/amazon-sagemaker-examples/tree/master/reinforcement_learning/rl_portfolio_management_coach_customEnv), which is the process of constant redistribution of capital into a set of different financial assets. The goal of a model like this is to maximize the return on investment while minimizing risk by using historic prices of stocks and current portfolio allocation.

**State**: Current stock portfolio, price history
**Action**: Buy, Sell Stocks
**Reward**: Positive when return is positive
        Negative when return is negative

You can also use [RL for Predictive Auto Scaling](https://aws.amazon.com/blogs/aws/amazon-sagemaker-rl-managed-reinforcement-learning-with-amazon-sagemaker/). You can optimize Auto Scaling instances to dynamically scale your service (such as Amazon EC2 instances), adding or removing capacity automatically according to conditions you define.

**State**: Current load, failed jobs, active machines
**Action**: Remove or add machines
**Reward**: Positive for successful transactions
        Negative for losing transactions

