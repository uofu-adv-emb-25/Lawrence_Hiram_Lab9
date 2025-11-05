// Invariants
1. Our FSM assumes ideal conditions, such as a ideal clock, contious power, sensors that will never wear down, etc.
2. For all tracks, only one train can be present. There will be a distance between trains, such that two or more trains will not be considered on the same track at a time.
3. Trains on each track only run in one direction.


// Varying Invariants
With the following PDF example in the lab README.md, during the ringing, arms_up state, there is a case in which the opposite direction approaches while the other train is departing, there is a safety hazard, because a train is approaching and there is no alarm of lowered barriers.


// Check your work
Hiram's FSM:
We found that this FSM faces the same issue as example FSM, looking above to see hazard.

Lawrence's FSM:
Unable to find hazard condition in FSM

// Prove it

| number | arms_down | alarm_on | northbound_present | southbound_present | north_approach | south_approach | north_depart | south_depart | ringing | safety_hazard |
|--------|-----------|----------|--------------------|--------------------|----------------|----------------|--------------|--------------|---------|---------------|
| 0      | 0         | 0        | 0                  | 0                  |       6        |       5         |       14       |      13        |         |               |
| 1      | 0         | 0        | 0                  | 1                  |     x     |        x        |              |              |         |               |
| 2      | 0         | 0        | 1                  | 0                  |      x    |         x       |              |              |         |               |
| 3      | 0         | 0        | 1                  | 1                  |      x          |        x        |              |              |         |               |
| 4      | 0         | 1        | 0                  | 0                  |       x       |       x         |              |              |         |               |
| 5      | 0         | 1        | 0                  | 1                  |      x        |        x        |              |              |         |               |
| 6      | 0         | 1        | 1                  | 0                  |     x          |        x        |              |              |         |               |
| 7      | 0         | 1        | 1                  | 1                  |      x        |        x        |              |              |         |               |
| 8      | 1         | 0        | 0                  | 0                  |       x        |        x        |              |              |         |               |
| 9      | 1         | 0        | 0                  | 1                  |       x       |        x        |              |              |         |               |
| 10     | 1         | 0        | 1                  | 0                  |       x       |         x       |              |              |         |               |
| 11     | 1         | 0        | 1                  | 1                  |       x       |         x       |              |              |         |               |
| 12     | 1         | 1        | 0                  | 0                  |        14      |         13       |              |              |         |               |
| 13     | 1         | 1        | 0                  | 1                  |        15      |         13       |              |              |         |               |
| 14     | 1         | 1        | 1                  | 0                  |        14      |         15       |              |              |         |               |
| 15     | 1         | 1        | 1                  | 1                  |        15      |        15        |              |              |         |               |

| number | invariant |
|--------|-----------|
| 16     |    Approach will proceed with a depart       |
| 17     |       Train present, no barrier    |
| 18     |       Train present, no alarm    |
| 19     |       Alarm is only on if there is a train present   |
| 20     |       Arms down only if there is a alarm    |
| 21     |           |
| 22     |           |
| 23     |           |
| 24     |           |
| 25     |           |

