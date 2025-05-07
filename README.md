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
