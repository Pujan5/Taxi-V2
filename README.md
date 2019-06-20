# Taxi-V2
Taxi-v2 is the environment that we have selected to test our different RL models. The agent is a taxi that has to

Drop off the passenger to the right location
Save passenger’s time by minimizing timesteps
Ensure passenger safety and follow traffic rules

Some of the key points we considered:

The agent should receive a high positive reward for a successful drop-off
The agent should be penalized if it tries to drop off a passenger in wrong locations
The agent should get a slight negative reward for not making it to the destination after every timestep


OpenAI gym helped recommend the optimal reward/penalty policy, allocating +20 points to a successful drop-off, -10 points for illegal pick-up and drop-off actions, and -1 point for every timestep the agent takes. There is only a slight negative penalty for timestep because we would prefer our agent to arrive later, instead of making wrong moves trying to reach to the destination as fast as possible.

The state space, the set of all possible situations the taxi could inhabit, is limited to the 5x5 grid for 25 possible taxi locations. In addition, there are 5 possible passenger locations (including the case when the passenger is in the taxi) and 4 destination locations. The locations are represented by R, G, Y, B in the grid. Therefore, our taxi environment has 5 x 5 x 5 x 4 = 500 total possible states.

The agent will encounter one of the 500 states and take a specific action. The action space, the set of all actions that our agent can take in a given state, is composed of six possible actions:

Move south
Move north
Move east
Move west
Pick-up
Drop-off

