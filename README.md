# formula1-experiments
Some experiments I'm doing with f1 (openf1 api can be used for this)

Main idea: given a track outline with track limits, can we learn what the optimal "racing line" is?
- how many iterations does it take for a model to figure out this line?
- does this give us optimal acceleration/braking points?
    - does this coincide with actual f1 telemetry data? -> super interesting i wanna find out
    - increase complexity: add DRS zones, ERS etc., tire wear/strategies, track temp evolution? -> this will be super hard
- we want to minimize the time it takes to complete the race -> would be ideal if you want to win
    - intuition tells me ERS in this case would be very interesting, since braking slows car, but is needed to increase battery
    - tire wear causes changes in grip -> we will add this later
- eventually: multi-car dynamics
    - somehow simulate dirty air(how do i do this?) and see how the model adapts lines

Implementation ideas:
- track layout can be represented as a black track w/ white limits like real world, or inverse of this
- current thoughts: input an image file -> we need to create a racetrack representation based on relative distances in the image
    - for this, we can have track(turn angle, distance, width) representation? -> complexity: how long is distance for turns vs straights?
- output also an image file, need to figure out how to rep a race line on the track, but we can just add a line on the input img this once we figure this out
    - current thought: line(point, distance from left)
- car rep: need speed, need to sense different angles to help w/ turning
