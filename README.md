# Deep-Skript

The deep neural network Skript script no one asked for or wanted--

My attempt at making a neural network (deep learning specifically) in vanilla Skript

## Features include

- Forward propagation (running)
- Backpropagation (training)
- Flexable network sizes

## How to use

Create the network with `DSCreateNetwork(inputs, layers, neurons-per-layer, outputs)` where all parameters are positive integers

Give the network training data with `DSPumpTraining(inputs, correct-answer)` where `inputs` is a list of inputs that matches the size of the network inputs and `correct-answer` is also a list of the desired outputs, which also need to match the size of the network outputs

Then you can actually train it with `DSTrainNetwork(epochs, rate)` where `epochs` is how many iterations to train it over and `rate` is the rate at which it learns

And finally run the network with `DSRunNetwork(inputs)` where `inputs` is a list of... inputs

## Simple example

Teaching it the rules of XOR

```
command /xor <int> <int>:
    trigger:
        DSCreateNetwork(2, 2, 2, 1)

        DSPumpTraining((0, 0), (0))
        DSPumpTraining((1, 0), (1))
        DSPumpTraining((0, 1), (1))
        DSPumpTraining((1, 1), (0))

        DSTrainNetwork(5, .1)

        send "%runNetwork((arg-1, arg-2))%"
```
And the network would look like this if you were to draw it

![What the above example would look like](https://github.com/LoganLilypad/Deep-Skript/raw/master/example.png)

## TODO
- Get it working properly
