# formula1-experiments
Some experiments I'm doing with f1

Main idea: given a track outline with track limits, can we learn what the optimal "racing line" is?
- how many iterations does it take for a model to figure out this line?
- does this give us optimal acceleration/braking points?
    - does this coincide with actual f1 telemetry data? -> super interesting
    - increase complexity: add DRS zones, ERS etc., tire wear/strategies, track temp evolution?
- we want to minimize the time it takes to complete the race
    - intuition tells me ERS in this case would be very interesting, since braking slows car, but is needed to increase battery
    - tire wear causes changes in grip
- eventually: multi-car dynamics
    - somehow simulate dirty air(?) and see how the model adapts lines
