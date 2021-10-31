### On-policy vs. Off-Policy
This division is based on whether you update your 𝑄 values based on actions undertaken according to your current policy or not. Let's say your current policy is a completely random policy. You're in state 𝑠 and make an action 𝑎 that leads you to state 𝑠′. Will you update your 𝑄(𝑠,𝑎) based on the best possible action you can take in 𝑠′ or based on an action according to your current policy (random action)? The first choice method is called off-policy and the latter - on-policy. 

[Q-learning vs. SARSA](https://stackoverflow.com/questions/6848828/what-is-the-difference-between-q-learning-and-sarsa)

![title](https://i.stack.imgur.com/wmFny.png)

Q-learning assumes the agent will act optimal in the `s'` state hence the $Max_aQ(s',a)$ (Maximum expected future reward)

SARSA will not assume optimal action but whatever action from the current policy.

### Policy-based vs. Value-based
In Policy-based methods we explicitly build a representation of a policy (mapping 𝜋:𝑠→𝑎) and keep it in memory during learning.

In Value-based we don't store any explicit policy, only a value function. The policy is here implicit and can be derived directly from the value function (pick the action with the best value).

**Actor-critic is a mix of the two.**

#### Model-based vs. Model-free
The problem we're often dealing with in RL is that whenever you are in state 𝑠 and make an action 𝑎 you might not necessarily know the next state 𝑠′ that you'll end up in (the environment influences the agent).

In Model-based approach you either have an access to the model (environment) so you know the probability distribution over states that you end up in, or you first try to build a model (often - approximation) yourself. This might be useful because it allows you to do planning (you can "think" about making moves ahead without actually performing any actions).

In Model-free you're not given a model and you're not trying to explicitly figure out how it works. You just collect some experience and then derive (hopefully) optimal policy.