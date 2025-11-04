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
| 0      | 0         | 0        | 0                  | 0                  |       6        |                |              |              |         |               |
| 1      | 0         | 0        | 0                  | 1                  |     17, 18     |                |              |              |         |               |
| 2      | 0         | 0        | 1                  | 0                  |      17, 18    |                |              |              |         |               |
| 3      | 0         | 0        | 1                  | 1                  |      17, 18          |                |              |              |         |               |
| 4      | 0         | 1        | 0                  | 0                  |        19       |                |              |              |         |               |
| 5      | 0         | 1        | 0                  | 1                  |               |                |              |              |         |               |
| 6      | 0         | 1        | 1                  | 0                  |               |                |              |              |         |               |
| 7      | 0         | 1        | 1                  | 1                  |               |                |              |              |         |               |
| 8      | 1         | 0        | 0                  | 0                  |               |                |              |              |         |               |
| 9      | 1         | 0        | 0                  | 1                  |               |                |              |              |         |               |
| 10     | 1         | 0        | 1                  | 0                  |              |                |              |              |         |               |
| 11     | 1         | 0        | 1                  | 1                  |              |                |              |              |         |               |
| 12     | 1         | 1        | 0                  | 0                  |              |                |              |              |         |               |
| 13     | 1         | 1        | 0                  | 1                  |        14      |                |              |              |         |               |
| 14     | 1         | 1        | 1                  | 0                  |        14      |                |              |              |         |               |
| 15     | 1         | 1        | 1                  | 1                  |        15      |                |              |              |         |               |

| number | invariant |
|--------|-----------|
| 16     |    Approach will proceed with a depart       |
| 17     |       Train present, no barrier    |
| 18     |       Train present, no alarm    |
| 19     |       Alarm is only on if there is a train present   |
| 20     |           |
| 21     |           |
| 22     |           |
| 23     |           |
| 24     |           |
| 25     |           |

