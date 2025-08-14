# THE PERCEPTRON: A PROBABILISTIC  MODEL  FOR INFORMATION STORAGE AND  ORGANIZATION IN THE BRAIN

## Questions

1) **What did the authors try to accomplish?** <br>

They examined how perceptrons could learn with different assumptions, architectures and learning theories of already existing research. Ultimately, they tried to accomplish: showing how a perceptron can learn and perform on various learning tasks.


2) **What were key elements of the approach?** <br>
- they compared different approaches for how learning might happen and adopted the "connectionists" view
- they compared different perceptorn "architectures" in terms of how weights are updated (the author speak of "value" for a cell)  

3) **What can you use for yourself?** <br>
- implement a perceptron


4) **What other references can you follow?** <br>
None

## Handwritten notes

There are 2 theories about how we store and use knowledge:
1) Knowledge is stored in representations. That is a 1:1 mapping code of say images. Each action we take (or a change of state, that can result in muscle moving or cognitive change) is the result of a direct mapping of experience -> action. Infers that if we crack the representation, we could retrieve all knowledge an organims knows.
=> unlikely that this is true with newly acquired evidence until now <br>
2) "connectionists": knowledge is stored in conncections and actions are the result of connections activatin
<br>
- in a large sample of inputs, inputs that are alike should trigger similar connections and vice verca
(if you input a picture of 2 cats vs. 1 cat & 1 dog, then likelihood is that the 2 cat images will activate the same path)

- the authors adopt a all-or-nothing model: either the neuron fires or not at all (it will fire if sum of stimuli is larger than a threshold psi)
- intersting: they think that there are feedback connections from every neuron to it's predecessor => on the way to backprop
- also they figured out that some neurons activate and some are dead if a certain output is triggered( output-dependent)
- then: for such a system to learn the activations must be changable

- is modern NN a alpha, beta, or gamma system?
- alpha: for each activation the neuron gains value
=> nah, then dead neurons could not exist
- beta: each neuron has a constant gain in proportion of it's activation
=> again, dead neurons could not exist
- gamma: active neurons gain in expense of non-active neurons (value of whole network is constant)
=> this allows dead neurons, but the assumption that the value/weight of whole network is constant is not the case for modern NN (otherwise we would not have exploding gradient problems), but it is close

- they assume a fixed threshold for a network (bias is not learned)
- Pa = expected proportion of A-cells activated
- Pc = prob that A-unit will respond to S2 (input) if it responded to S1

- they actually talk early about RL
- 3 wys of perceptron learning:
    1) experimenter forces activation of ouput neuron x, for stimuli y <br>
    2) experimenter reinforces a dersired activation for a set of inputs positively, and negative for a undesired activation <br>
    3) giving different classes of inputs and trying to get the neruon to predict the correct class (classification)

- bivalent systems: positive reinforcement increases all active neurons value, and negative values added to all off neurons
- analogous for negative reinforcement
=> this is capable of learning well, close to modern NN

**question: how is this different from backprop?**

- this simple perceptron could already get audio & video as input and perform name classification tasks
- perceptron is capable of: trial and error learning when using a bivalent system

