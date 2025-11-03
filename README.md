// Invariants
1. Our FSM assumes ideal conditions, such as a ideal clock, contious power, sensors that will never wear down, etc.
2. For all tracks, only one train can be present. There will be a distance between trains, such that two or more trains will not be considered on the same track at a time.
3. Trains on each track only run in one direction.


// Varying Invariants
With the following PDF example in the lab README.md, during the ringing, arms_up state, there is a case in which the opposite direction approaches while the the other train is departing, there is a safety hazard, because a train is approaching and there is no alarm of lowered barriers.


// Check your work
Hiram's FSM:
We found that this FSM faces the same issue as example FSM, looking above to see hazard.

Lawrence's FSM:
Unable to find hazard condition in FSM
