# Assignment 3 – Lottery Scheduling

## 1. Setup
- Number of child processes: 3
- Ticket allocation:
  - Child 4: 10 tickets
  - Child 5: 20 tickets
  - Child 6: 40 tickets
- Workload: Each child runs a CPU-bound loop performing 100,000,000 iterations.

## 2. Test Program
- Program used: `testlottery.c`
- Description: Each child prints how many “work units” it completed after finishing its CPU-bound loop.

## 3. Observed Results
Example output from running `testlottery`:


- The results show that processes with more tickets run more often.
- CPU share roughly corresponds to the proportion of tickets: Child 6 (40 tickets) runs about four times as much as Child 4 (10 tickets) over the long term.

## 4. Notes
- Randomness implemented with an in-kernel Linear Congruential Generator (LCG) PRNG.
- Short runs may have slight deviations due to randomness.
- Longer runs converge closer to expected CPU share ratios.
