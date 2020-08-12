# Deep-Skript

The deep neural network Skript script no one asked for or wanted--

My attempt at making a neural network (deep learning specifically) in vanilla Skript

## Features include

- Forward propagation (running)
- Backpropagation (training)
- Flexable network sizes

## How to use

Create the network with `createNetwork(inputs, layers, neurons-per-layer, outputs)` where all parameters are positive integers

Give the network training data with `addTraining(inputs, correct-answer)` where `inputs` is a list of inputs that matches the size of the network inputs and `correct-answer` is also a list of the desired outputs, which also need to match the size of the network outputs

Then you can actually train it with `trainNetwork(epochs, rate)` where `epochs` is how many iterations to train it over and `rate` is the rate at which it learns

And finally run the network with `runNetwork(inputs)` where `inputs` is a list of... inputs

## Simple example

Teaching it the rules of XOR

```
command /xor <int> <int>:
    trigger:
        createNetwork(2, 2, 2, 1)

        addTraining((0, 0), (0))
        addTraining((1, 0), (1))
        addTraining((0, 1), (1))
        addTraining((1, 1), (0))

        trainNetwork(5, .1)

        send(runNetwork((arg-1, arg-2)))
```

## TODO
- Get it working properly
