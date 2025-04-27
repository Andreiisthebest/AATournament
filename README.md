# Trust but Verify - Advanced Prisoner's Dilemma Strategy

**Trust but Verify** is a highly responsive, pattern-aware strategy designed to maximize cooperation while minimizing exploitation. It combines Tit-for-Tat principles with advanced opponent modeling and adaptive forgiveness to outperform random and unpredictable opponents.

## Part 1: Core Principles

**1. Start Friendly (Initial Cooperation)**
+ Always cooperates on the first move to encourage mutual cooperation.

**2. Early Game Mirroring**
+ For the first 5 moves, it simply mirrors the opponent's last move to gather initial data.

**3. Opponent Behavior Analysis**
+ **Cooperation Rate:** Tracks the opponent's cooperation rate over the last 10 moves.
  + If >70% cooperation, it keeps cooperating (rewarding nice behavior).
  + If <30% cooperation, it defects (punishing exploiters).
+ **Defect Streak Detection:** If the opponent defects 3+ times in a row, it retaliates aggressively.

**4. Pattern Recognition**
+ Detects alternating patterns (e.g., D-C-D-C), which are common in random opponents.
+ If the opponent alternates too much (>10 changes in 15 moves), it exploits them by defecting when they cooperate and cooperating when they defect.

**5. Controlled Forgiveness**
+ Every 4th move, it forgives a defection (cooperates even if the opponent defected last).
+ If it has defected 8 times in a row, it resets and cooperates to break deadlocks.

## Part 2: Opponent Selection Strategy

For the second part of the tournament, Trust but Verify extends its strategy to intelligently select opponents:

**1. Opponent Scoring System**
+ Calculates a composite score for each potential opponent based on:
  + Average points earned per round (70% weight)
  + Cooperation rate (30% weight)

**2. Strategic Opponent Selection**
+ Prioritizes opponents who yield the highest point returns
+ Balances between exploitation (playing with cooperative opponents) and exploration (trying new opponents)
+ Gives new opponents a moderate starting score to encourage initial play

**3. Resource Management**
+ Carefully tracks the number of rounds played with each opponent
+ Avoids opponents who have reached the maximum allowed rounds (200)
+ Defaults to the current opponent if no better alternatives are available

**4. Point Optimization**
+ Calculates expected value from each opponent based on historical interactions
+ Seeks to maximize tournament points rather than just win-loss metrics
+ Adapts opponent selection based on observed behavior patterns