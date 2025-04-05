# Trust but Verify - Advanced Prisoner's Dilemma Strategy


**Trust but Verify** is a highly responsive, pattern-aware strategy designed to maximize cooperation while minimizing exploitation. It combines Tit-for-Tat principles with advanced opponent modeling and adaptive forgiveness to outperform random and unpredictable opponents.

**Core Principles**:

**1. Start Friendly (Initial Cooperation)**

+ Always cooperates on the first move to encourage mutual cooperation.

**2. Early Game Mirroring**

+ For the first 5 moves, it simply mirrors the opponent’s last move to gather initial data.

**3. Opponent Behavior Analysis**

 **Cooperation Rate:** Tracks the opponent’s cooperation rate over the last 10 moves.

+ If >70% cooperation, it keeps cooperating (rewarding nice behavior).

+ If <30% cooperation, it defects (punishing exploiters).

**Defect Streak Detection:** If the opponent defects 3+ times in a row, it retaliates aggressively.

**Pattern Recognition**

+ Detects alternating patterns (e.g., D-C-D-C), which are common in random opponents.

+ If the opponent alternates too much (>10 changes in 15 moves), it exploits them by defecting when they cooperate and cooperating when they defect.

**Controlled Forgiveness**

+ Every 4th move, it forgives a defection (cooperates even if the opponent defected last).

+ If it has defected 8 times in a row, it resets and cooperates to break deadlocks.