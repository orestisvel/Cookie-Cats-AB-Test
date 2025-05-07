# Cookie-Cats-AB-Test

In this project, we will conduct an A/B test on data from the mobile puzzle game Cookie Cats.

Cookie Cats is a popular puzzle game developed by Tactile Entertainment, first released on April 27, 2016. With over 1 million downloads on Google Play alone, the game features a classic "connect-three" mechanic, where players match tiles of the same color to clear the board and advance through increasingly challenging levels.

As players progress through Cookie Cats, they occasionally hit gates that either require a wait or an in-app purchase to continue. These gates not only encourage spending but also give players a forced break, which may help sustain long-term enjoyment.

Originally, the first gate appeared at level 30. In this dataset, players have been randomly assigned to a Control Group (version 1, gate at level 30 as originally designed) and a Treatment Group (version 2, with the gate moved to level 40).

The dataset includes features such as the number of rounds played, and whether a player returned to the game the day after installation (Day 1 retention) and one week later (Day 7 retention). We’ll apply data analysis and hypothesis testing to determine whether this gate change had a significant effect on player retention and behavior.

We began by importing the main data analysis libraries: NumPy, pandas, seaborn, and matplotlib. Then, we loaded the data and continued with some exploratory data analysis.

Our data set consists of 90189 samples and 5 columns.

**Features**


*   userid : A unique identifier assigned to each player.

*   version : Indicates the experimental group the player was assigned to, either gate_30 or gate_40.

*   sum_gamerounds : The total number of game rounds played by the player during the first **14 days** after install.

*   retention_1 : A boolean value indicating whether the player returned to play the game one day after installation.

*   retention_7 : A boolean value indicating whether the player returned to play the game seven days after installation.

It is also very well balanced between the two versions (gate_30 and gate_40), with 44,700 samples for gate_30 and 45,489 for gate_40.

We used the describe() function to obtain a statistical summary of the number of game rounds

![image](https://github.com/user-attachments/assets/95b49e48-f080-44b3-9479-b4be6f86b545)

As shown in the summary, there is an extreme outlier: while most players played around 51 rounds, one player played 49,854 rounds.

![image](https://github.com/user-attachments/assets/5c60d76d-6167-48cb-bcf1-dd3924c07ec3)

Since we're focusing on casual player behavior, the extreme outlier with 49,854 game rounds would heavily skew the distribution without providing meaningful insights. Therefore, we removed it from the analysis.


Next, we analyzed the total number of game rounds. We plotted a graph to visualize the distribution of game rounds played by players, separated by game version.

![image](https://github.com/user-attachments/assets/2a3e0145-e109-499f-a713-c1f30d7d6683)

As we can see, the blue line (Gate 30) and the red line (Gate 40) follow a very similar pattern overall. However, if we zoom in on the 30–40 game round range, an interesting shift occurs: the blue line clearly surpasses the red.

![image](https://github.com/user-attachments/assets/96ebeaa5-a4f3-4a9f-9e92-9f7ae77b1c40)


This could suggest that, although players in Gate 30 encountered the gate earlier, those who pushed through it were more engaged, resulting in more users continuing beyond round 30 compared to Gate 40.

In contrast, players in Gate 40 had not yet encountered the gate during this range, yet their drop-off rate was slightly higher. After round 40, both groups return to a similar declining trend, which is expected as fewer players reach higher round counts.

Then we calculated distribution statistics for the number of game rounds per player, split by game version. This includes some percentiles from 1% to 99%, along with the mean, standard deviation, minimum, and maximum values. 

![image](https://github.com/user-attachments/assets/e67c9f50-1de5-4025-a76d-86e9cb117fb0)


Next, we analyzed retention rates. 

![image](https://github.com/user-attachments/assets/7ba7b8c7-8e6d-469c-a1f6-b26b6de431c8)

Based on the chart, there were no visually noticeable differences between the two versions for either Day 1 or Day 7 retention.

![image](https://github.com/user-attachments/assets/ce0c6a77-c640-4e15-a32f-9c18516031e9)

Version 1 --- Gate 30                                                         Version 2 --- Gate 40

Retention_1 = 44.82% of players returned the next day                         Retention_1 = 44.23% returned the next day
Retention_7 = 19.02% returned one week later                                  Retention_7 = 18.20% returned after one week

Version 2 --- Gate 40

Retention_1 = 44.23% returned the next day
Retention_7 = 18.20% returned after one week



