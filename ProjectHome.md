AnimObj class inherits from OBJModel class from OBJ Loader lib to add the feature of transforming the model, by manipulating its vertexes, in order to achieve the shape of another model.

One example (a kind for what I've used it): I have an OBJ model of an opened hand, and I wish perform an animation in which the open hand become closed. For that, I've another OBJ, that is the closed hand model. So what I have to do is load the opened hand model with AnimObj class and use its methods to say "I want this opened hand to turn into a closed one", so the argument will be the closed hand model and the animation will be performed.

To achieve this what the class does is a linear interpolation into the model mesh vertexes. Take care!: how OBJ doesn't support bones, the interpolation is performed in the mash, what can cause some "bizarres" effects.


OBJ Loader project: http://code.google.com/p/saitoobjloader/

Example of usage:

```

public HandGraph(PApplet processing, Hand hand) {

   this.model = new AnimObj(processing, "dir/opened_hand.obj");
}

...

void nextSign(OBJModel nextHand) {

    this.model.setNextPose(nextHand);
    this.model.startAnim();
}
```

PS: it's was done with the OBJ Loader rev20 at August 9, 2009.

I've used this lib to make the shape hand transformation in the following application:
http://www.youtube.com/watch?v=PGrSLGAFAC8

Leonardo Leite