# Markov Melodies
This repo contains various studies for using markov chaining to generate melodies and rhythms.  The technique is inspired by [Andrew Sorensen's "The Concert Programmer" talk](https://www.youtube.com/watch?v=yY1FSsUV-8c).  Though he uses a scheme-based language I have adapted these ideas to Ruby and used SonicPi to implement them here.

## Generative Melodies using Markov Chaining

This represents one way of creating generative music by doing a randomized walk on a graph where each node represents a note state in a scale and each edge represents a transition.  Edges are chosen randomly at different points in the loops (for example, once per measure or once per beat event), but repetition of edges allows the simulation of weighted choices at each transition.

![](https://raw.githubusercontent.com/omardelarosa/markov-melodies/master/_images/bells-fig1.png)

For example, if you are on the `0` note of the scale and there are 3 edges to note `3` and 1 to note `5`.  This would represent a `0.75` probability of going to note `3` and `0.25` of going to note `5` using a random "choice" function during each transition.

### The Weeknd - "High For This"
You can see an example of how this works with a live code video I made using this technique and vocals from "High For This" by The Weeknd here:

[![Using markov chaining to create instrumental music for The Weeknd's "High For This"](http://img.youtube.com/vi/GhzMj-6Js2Y/0.jpg)](https://youtu.be/GhzMj-6Js2Y)